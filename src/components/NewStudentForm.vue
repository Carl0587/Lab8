<template>
    <div>

    </div>
</template>

<script>
    export default {
        name: 'NewStudentForm',
        data() {
            return {
                newStudentName: '',
                newStarID: '',
                errors: []
            }
        },
        methods: {
            addStudent() {
                this.errors = []
                if (this.newStudentName && this.newStarID) {
                    let student = { name: this.newStudentName, starID: this.newStarID, present: false }
                    this.$emit('student-added', student)
                    this.newStudentName = ''
                    this.newStarID = ''
                } else {
                    this.errors.push('Name and StarID are required.')
                }
            }
        }
    }

</script>

<style>
    /* Write any styles for elements in this component here  */
</style>

