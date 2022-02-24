<template>
 <div class="home pa-6">

    <v-list
      flat
    >
    <div v-for="task in tasks" :key="task.id">
        <v-list-item @click="doneTask(task.id)">
        <template v-slot:default>
            <v-list-item-action>
            <v-checkbox :input-value="task.done"></v-checkbox>
            </v-list-item-action>

            <v-list-item-content>
            <v-list-item-title>{{ task.title}}</v-list-item-title>
            </v-list-item-content>
        </template>
        </v-list-item>
        <v-divider></v-divider>
    </div>
  
    </v-list>
 </div>
</template>

<script>

  export default {
    name: 'Todo',

    data() {
        return {
            tasks:[
                { 
                    id: 1,
                    title: 'Mafor',
                    done: false
                }, 
                { 
                    id: 2,
                    title: 'Mafor Ke',
                    done: false
                }, 
                { 
                    id: 3,
                    title: 'Mafor Pa',
                    done: false
                },
            ]
        }
    },
    methods: {
        doneTask(id) {
            let task = this.tasks.filter(task => task.id === id)[0]
            task.done = !task.done
        }
    }
  }
</script>
