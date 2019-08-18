<template>
    <section class ="recipes">
        <Recipe
        v-for="recipe in recipes"
        :key = "recipe.id"
        :thumbnail ="recipe.thumbnail"
        :title="recipe.title"
        :id="recipe.id"
        :previewText="recipe.previewText" />        
    </section>
</template>
<script>
import Recipe from '@/components/Recipe'
export default {
    components:{
        Recipe
    },
    asyncData(){
        return new Promise((resolve,reject)=>{
            setTimeout(()=>{
                resolve({
                    recipes:[{
                        id:"1",
                        title:"Delicious Pizza",
                        previewText:"Awesome Pizza!",
                        thumbnail:"https://sethlui.com/wp-content/uploads/2013/10/best-singapore-food-682.jpg"
                    },
                    {
                        id:"2",
                        title:"Sea food salad",
                        previewText:"Very tasty indeed!",
                        thumbnail:"https://assets3.thrillist.com/v1/image/2797371/size/tl-horizontal_main_2x.jpg"
                    }]
                })
            },1500)
        })
    }
}
</script>
<style scoped>
    .recipes{
        display:flex;
        flex-flow:row wrap;
        justify-content:center;
        align-items:center;
    }    
</style>