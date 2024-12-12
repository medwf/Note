```python
import asyncio

# code 1
await asyncio.sleep(2, result='hello') # sleep 2s and disply hello


# code 2
import asyncio
import time

async def brewcoffee():

    print('Start brewCoffee!')

    # we should to specific where coroutines should await.

    # time.sleep() is not awaitable.

    # time.sleep(3)

    # so we use asyncio.sleep()

    await asyncio.sleep(3)

    print('End brewCoffee ?')

    return 'coffee ready'

  

async def toastBaget():

    print('start toast Baget !')

    # we should to specific where coroutines should await.

    # time.sleep() is not awaitable.

    # time.sleep(3)

    # so we use asyncio.sleep()

    await asyncio.sleep(2)

    print('End toast Baget ?')

    return 'Baget toast'

  

async def run():

    start_time = time.time()

    # r_coffee = brewcoffee()

    # t_Baget = toastBaget()

    # and we can run 2 coroutines function by using gather.

    batch = asyncio.gather(brewcoffee(), toastBaget())

  

    # test where a await is stay pause. in await not in gather.

    print("before await", dir(batch), type(batch))

    r_coffee, t_Baget = await batch

    print('after await')

  

    # or can make task by using create_task

    cf = asyncio.create_task(brewcoffee())

    ts = asyncio.create_task(toastBaget())

    # cf and ts is just an instance of 'asyncio.tasks._GatheringFuture'

    f = await cf

    t = await ts

    # f and t have a result of those function.

  
  

    print(f"code take {time.time() - start_time:.2f} s")

    # print(f"result is {r_coffee}, {t_Baget}")

    print(f'result : {f}, {t}')

  

if __name__ == '__main__':
	# to run a async function 
    asyncio.run(run())
```