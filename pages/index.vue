<template>
  <div>
    <h1>Example VueJS: Conditional Presentation</h1>
    <p class="green" v-if="show">
      This paragraph when is True
    </p>
    <p class="red" v-if="!show">
      This paragraph when is False
    </p>


    <h1>Example VueJS: Using Loop</h1>
    <ul v-if="computerLang.length">
      <li v-for="item in computerLang" :key="item.id">
        {{item.language}}
      </li>
    </ul>
    <p v-else>Not any item on Menu, V-else is working</p>


    <h1>Example VueJS: Event Handling</h1>
    <p>Value of counter : <span style="font-size:20px">{{ counter }}</span></p>
    <button class="button" v-on:click="addCounter(1)">Add</button>
    <button class="button" v-on:click="reduceCounter(1)">Subtract</button>
    <button class="button" v-on:click="resetCounter()">Reset</button>
  
    <h1>Example VueJS: Input Form</h1>
    <label for="name">Name</label>
    <input id="name" v-model="name" placeholder="Input your name" />
    <p>Gender</p>
    <div>
      <input type="radio" id="male" value="Male" v-model="gender" />
      <label for="male">Male</label><br>
      <input type="radio" id="female" value="Female" v-model="gender" />
      <label for="female">Female</label><br>
    </div>
    <p>Hobbies</p>
    <div>
      <input type="checkbox" id="reading" value="Reading" v-model="hobbies" />
      <label for="reading">Reading</label><br>
      <input type="checkbox" id="listening" value="Listening" v-model="hobbies" />
      <label for="listening">Listening a Music</label><br>
      <input type="checkbox" id="watching" value="Watching" v-model="hobbies" />
      <label for="watching">Watching a Movie</label><br>
      <input type="checkbox" id="gaming" value="Gaming" v-model="hobbies" />
      <label for="gaming">Playing Game</label><br>
    </div>
    <br>
    <button v-on:click="submit">Submit</button>

  
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      computerLang:[
        // {id: 1, language:"Java"},
        // {id: 2, language:"Python"},
        // {id: 3, language:"C/C++"},
        // {id: 4, language:"C#"},
        // {id: 5, language:"JavaScript"}
      ],
      counter:0,
      gender:'',
      name:'',
      hobbies:[],
    };
  },
  methods: {
    addCounter(num) {
      this.counter +=num;      
    },
    reduceCounter(num){
      this.counter -=num;   
    },
    resetCounter(){
      this.counter =0;
    },
    submit(){
      console.log(this.name, this.gender, this.hobbies)
    }
  },
};
</script>

<style>
.red{
  color:red;
}
.green{
  color:green;
}
.button{
  border-radius: 50px;
  background-color:azure;
}
</style>
