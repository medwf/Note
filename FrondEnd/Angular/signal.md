# Angular Properties vs Signals: Key Differences with Examples

In Angular, you can manage component state in two main ways: traditional properties and the newer Signals (introduced in Angular 16). Here's a comparison with examples:

## Traditional Properties

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-counter',
  template: `
    <p>Count: {{ count }}</p>
    <button (click)="increment()">Increment</button>
  `
})
export class CounterComponent {
  count = 0; // Traditional property

  increment() {
    this.count++;
  }
}
```

## Signal-based Approach

```typescript
import { Component, signal } from '@angular/core';

@Component({
  selector: 'app-counter',
  template: `
    <p>Count: {{ count() }}</p>
    <button (click)="increment()">Increment</button>
  `
})
export class CounterComponent {
  count = signal(0); // Signal

  increment() { this.count.update(current => current + 1); }
}
```

## Key Differences:

1. **Declaration**:
   - Traditional: `count = 0`
   - Signal: `count = signal(0)`

2. **Template Usage**:
   - Traditional: `{{ count }}`
   - Signal: `{{ count() }}` (note the function call)

3. **Updates**:
   - Traditional: Direct assignment (`this.count++`)
   - Signal: Using `set()` or `update()` methods

4. **Change Detection**:
   - Traditional: Angular checks the whole component for changes
   - Signal: Angular knows exactly what changed (more efficient)

## Advanced Signal Example with Computed Values:

```typescript
import { Component, signal, computed } from '@angular/core';

@Component({
  selector: 'app-user',
  template: `
    <input [(ngModel)]="firstName" placeholder="First name">
    <input [(ngModel)]="lastName" placeholder="Last name">
    
    <p>Full name: {{ fullName() }}</p>
    <p>Name length: {{ nameLength() }}</p>
  `
})
export class UserComponent {
  firstName = signal('');
  lastName = signal('');
  
  // Computed signal that updates automatically
  fullName = computed(() => `${this.firstName()} ${this.lastName()}`);
  
  // Another computed signal
  nameLength = computed(() => this.fullName().length);
}
```

Signals provide fine-grained reactivity, allowing Angular to optimize change detection by only updating what's necessary. They're particularly useful for complex state management and derived values.