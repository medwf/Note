``` javascript

jQuery(document).ready(

function () {

jQuery(".thumbs-rating-container").each(

function (b) {

var a = jQuery(this).data("data-content-id");

var c = "recipe_vote_" + a;

console.log(c, 'loop');

  

if (localStorage.getItem(c)) {

if (localStorage.getItem("recipe_vote_" + a + "-1")) {

jQuery(this).find(".thumbs-rating-up").addClass("thumbs-rating-voted")

}

if (localStorage.getItem("recipe_vote_" + a + "-0")) {

jQuery(this).find(".thumbs-rating-down").addClass("thumbs-rating-voted")

}

}

})

});

```

<!-- Footer Theme output -->

<!-- <script>

</> -->