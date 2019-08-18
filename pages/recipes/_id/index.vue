<template>
    <section class="single-recipe">
        <h1>{{recipe.title}}</h1>
        <div>
            <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.previewText">
        </div>
        <p>{{recipe.description}}</p>
    </section>
</template>
<script>
export default {
    asyncData(context){
        return new Promise((resolve,reject)=>{
            setTimeout(()=>{
                resolve({
                    recipe:[{
                        id:"1",
                        title:"Delicious Pizza",
                        previewText:"Awesome Pizza!",
                        description : "this is really a delicious meal!",
                        thumbnail:"https://sethlui.com/wp-content/uploads/2013/10/best-singapore-food-682.jpg"
                    },
                    {
                        id:"2",
                        title:"Sea food salad",
                        previewText:"Very tasty indeed!",
                        description : "this is really a delicious meal!",
                        thumbnail:"https://assets3.thrillist.com/v1/image/2797371/size/tl-horizontal_main_2x.jpg"
                    }].find(el => el.id === context.params.id)
                })
            },1500)
        })
    }
}
</script>
<style scoped>
    .single-recipe{
        display:flex;
        flex-flow:column;
        justify-content:center;
        align-items:center;
        text-align:center;
        padding:30px;
    }
    .recipe-image{
        width:100%;
    }
</style>