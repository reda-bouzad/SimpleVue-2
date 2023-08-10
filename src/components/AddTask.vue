<template>
    <form class="my-form" action="">
        <input class="my-input" type="text" placeholder="Add Task">
        <input class="my-input" type="text" placeholder="Day & Time">
        <div class="checkbox">
            <p> <b>Set reminder</b>  </p>
            <input type="checkbox" name="" id="">
        </div>
        <input class="submit-btn" type="submit">
    </form>
</template>

<script>
    export default{
        name: "AddTask"
    }
</script>

<style scoped>
    .my-form{
        padding: 10px;
        display: flex;
        flex-direction: column;
        row-gap: 20px;
    }
    .my-input{
        padding-top: 10px;
        padding-bottom: 10px;
        border-radius: 6px;
        border: 2px solid rgb(122, 119, 119);
    }
    .checkbox{
        display: flex;
        justify-content: space-between;
    }
    .submit-btn{
        background-color: #4682a9;
        color: white;
        padding-top: 8px;
        padding-bottom: 8px;
        border: none;
        font-size: large;
        font-family: Verdana, Geneva, Tahoma, sans-serif;
        margin-bottom: 20px;
        border-radius: 10px;
    }
    .submit-btn:hover{
        cursor: pointer;
    }

</style>