<template>
    <div class="contact-details">
        <h1 class="heading">Contact Details</h1>
        <p><strong>Name: </strong>{{ name }}</p>
        <p><strong>Father: </strong>{{ father }}</p>
        <p><strong>Address: </strong>{{address}}</p>
    </div>
</template>

<script>
export default{
    props:["name","father","address"],
    data(){
        return{
        }
    }
}
</script>

<style scoped>
.contact-details{
    border: 1px solid gray;
    margin: 11px,22px;
    padding: 22px;
    text-align:left;
    
}
.heading{
    color:rgb(0, 73, 107)
}
</style>