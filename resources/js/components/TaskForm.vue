<template>

            <div class="col-md-8">
                <div class="card card-default">
                    <div class="card-header">Task Form </div>

                    <div class="card-body">
                        <Form action="./api/task" method="POST">
                            <div class="form-group">
                                <input type="text" name="title" v-model="title" placeholder="Task title" class="form-control">
                            </div>
                            <div class="form-group">
                                <input type="submit" value="Add Task" class="btn btn-info">
                            </div>
                        </form>
                    </div>
                </div>
            </div>

</template>

<script>
    export default {
        data(){
            return {
                title: ''
            }
        },
        mounted() {
            console.log('Component mounted.')
        },

        method:{
            addTask(){
                axios.post('./apo/task',{title:'this.title});
                Event.$emit('taskCreated',{title:'this.title});

            }
        }
    }
</script>
