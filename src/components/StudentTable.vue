<template>
    <div>
        <div class="alert alert-danger" v-show="errors && errors.length > 0">
            <li v-for="error in errors" v-bind:key="error">{{ error }}</li>
        </div>

        <div class="card add-student m-2 p-2">
            <form>
                <h4 class="card-title">Add new student</h4>

                <div class="form-group">
                    <label for="name">Name</label>
                    <input id="name" class="form-control" v-model.trim="newStudentName">
                </div>
                <div class="form-group">
                    <label for="starID">Star ID</label>
                    <input id="starID" class="form-control" v-model.trim="newStarID">
                </div>
                <button class="btn btn-primary" v-on:click.prevent="addStudent">Add</button>
            </form>
        </div>


    </div>
</template>

<script>
    export default {
        name:'StudentTable',
        props:{
            students:Array
        },
        methods:{
            checked(student){
                this.$emit('student-present', student)

            }
        }
    }

</script>

<style>
    #student-table {
        max-height: 500px;
        overflow: scroll;
    }

    .present-true {
        color: gray;
        font-style: italic;
    }

    .present-false {
        font-weight: bold;
    }
    /* Write any styles for elements in this component here  */
</style>

