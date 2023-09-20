<template>
    <div class="container">
        <div class="row" >
            <div class="col-md-4" >
                <!-- inline binding button handler -->
                <button @click='clickMe("david")'>Click Me</button>
                <button @click="count++">Count Me {{ count }}</button>
                <button @click="addButton">Add button</button>
                <button @click="showStudent">Show student</button>
                <button @click="increaseButton">Increase button</button>

            </div>
            <!-- added data with formal javascript -->
            <div class="col-md-4" id="div1">
                
            </div>
            <div class="col-md-4">
                <table class="table table-success" v-if="status">
                    <thead>
                        <th>Name</th>
                        <th>Age</th>
                        <th>Address</th>
                    </thead>
                    <tbody>
                        <tr v-for="student in students" :key="student">
                            <td>{{ student.name }}</td>
                            <td>{{ student.age }}</td>
                            <td>{{ student.address }}</td>
                        </tr>
                    </tbody>
                   
                </table>
            </div>
            <!-- added data with method (using v-html tag)-->
            <div class="col-md-4" v-html="element">
                
            </div>
        </div>
    </div>
</template>
<script setup>
import {ref} from 'vue'
const count= ref(0)
 function addButton(){
    const div1 = document.getElementById('div1')
    div1.innerHTML +="<button>Button 1</button>"
 }
</script>
<script>
    export default{
        name:'MethodComponent',
        data(){
            return {
                // count:0,
                element:'',
                students:[
                    {
                        name:"David",
                        age:20,
                        address:'Mdy'
                    },
                    {
                        name:"Kathy",
                        age:20,
                        address:'Ygn'
                    },
                    {
                        name:"Dar Dar",
                        age:21,
                        address:'Mdy'
                    },
                ],
                status:false,
            }
        },
        methods:{
        clickMe(name){
            // console.log('Click Me' + name)
            alert("Click Me "+name)
        },
        increaseButton(){
            this.element = '<button id="delete">Delete</button>'
        },
        showStudent(){
            this.status = true
        },
        addDelete(){
            console.log("In add delete")
        }
        },
        mounted(){
            document.getElementById('delete').addEventListener('click',this.addDelete)
        }
    }
</script>