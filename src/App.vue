<template>
  <div class="container text-center">
    <div class="row grid">
      <!--Bind starts here-->
      <div class="col-4 col">
        <div class=" card">
          <div class="card-header">
            <h3>Bind</h3>
          </div>
          <div class="card-body">
            <div>{{ lastname }} {{ firstname }}</div>
            <div v-text="channel"></div>
            <div v-html="great"></div>
            <div v-html="hack"></div>
            <h3 v-bind:id="headingId">Heading</h3>
            <button v-bind:disabled="isDiabled">Bind</button>
          </div>
        </div>

      </div>
      <!--Bind to  ends here-->

      <!--Bind classes starts here-->
      <div class="col col-4 ">
        <div class=" card">
          <div class="card-header">
            <h3>Bind classes</h3>
          </div>
          <div class="card-body">
            <h3 class="underline">Underlined text</h3>
            <h3 class="underline" v-bind:class="status">Status </h3>
            <h3 v-bind:class="ispromoted && 'promoted'">promoted movie </h3>
            <h3 v-bind:class="isSoldOut ? 'soldeout' : 'soldoutnew'">sold Out movie</h3>
            <h3 v-bind:class="['new', 'promoted']">Newly promoted movie</h3>
            <h3 v-bind:class="[ispromoted && 'promoted', isSoldOut ? 'soldeout' : 'soldoutnew']">Array conditional Movie
            </h3>
            <h3 v-bind:class="{
              promoted: ispromoted,
              soldoutnew: !soldeout,
            }">Object conditional movie</h3>
          </div>
        </div>
      </div>
      <!--Bind classes ends here-->

      <!--Bind styles starts here-->
      <div class="col col-4 ">
        <div class=" card">
          <div class="card-header">
            <h3>Bind styles</h3>
          </div>
          <div class="card-body">
            <h3 v-bind:style="{
              color: highlightColor,
              'font-size': headerSize + 'px',
              padding: '20px'
            }">Inline style</h3>
            <h3 v-bind:style="headerStyleObject">Style Object</h3>
            <h3 v-bind:style="[baseStyleObject, successStyleObject]">Success style</h3>
            <h3 v-bind:style="[baseStyleObject, dangerStyleObject]">Success style</h3>
          </div>
        </div>
      </div>
      <!--Bind styles ends here-->

      <!--v-bind shorthand starts here-->
      <div class="col col-4">
        <div class=" card">
          <div class="card-header">
            <h3>v-bind shorthand</h3>
          </div>
          <div class="card-body">
            <h3 :style="{
              color: highlightColor,
              'font-size': headerSize + 'px',
              padding: '20px'
            }">Inline style</h3>
            <h3 :style="headerStyleObject">Style Object</h3>
            <h3 :style="[baseStyleObject, successStyleObject]">Success style</h3>
            <h3 :style="[baseStyleObject, dangerStyleObject]">Success style</h3>
            <h3 class="underline" :class="status">Status </h3>
            <h3 :class="ispromoted && 'promoted'">promoted movie </h3>
          </div>
        </div>
      </div>
      <!--v-bind shorthand ends here-->

      <!--Conditional Rendering-1 starts here-->
      <div class="col col-4 ">
        <div class=" card">
          <div class="card-header">
            <h3>Conditional Rendering-1</h3>
          </div>
          <div class="card-body">
            <h3 v-if="num === 0">The number is zero</h3>
            <h3 v-else-if="num > 0">The number is positive</h3>
            <h3 v-else-if="num < 0">The number is positive</h3>
            <h3 v-else>Not a number</h3>

            <div v-if="display">
              <h3>manjula</h3>
              <h3>codeVolution</h3>
              <h3>Vue</h3>
            </div>
          </div>
        </div>
      </div>
      <!--Conditional Rendering-1 ends here-->
      <!--Conditional Rendering-11 starts here-->
      <div class="col col-4 ">
        <div class=" card">
          <div class="card-header">
            <h3>Conditional Rendering-11</h3>
          </div>
          <div class="card-body">
            <h3 v-show="showElement">Uisng v show</h3>
            <h3 v-if="showElement">Uisng v-if</h3>
          </div>
        </div>
      </div>
      <!--Conditional Rendering-11 ends here-->

      <!--List Rendering starts here-->
      <div class="col col-4 ">
        <div class=" card">
          <div class="card-header">
            <h3>List Rendering</h3>
          </div>
          <div class="card-body">
            <div>
              <table class="table">
                <thead>
                  <tr>
                    <th>S.No</th>
                    <th>Names</th>
                  </tr>
                </thead>
                <tbody v-for="(name, index) in names" :key="name">
                  <tr>
                    <td>{{ index }}</td>
                    <td>{{ name }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
            <div>
               <table class="table">
                <thead>
                  <tr>
                    <th>S.No</th>
                    <th>First Name</th>
                    <th>Last Name</th>
                    <th>Relation</th>
                  </tr>
                </thead>
                <tbody v-for="(name, number) in fullNames" :key="name.first">
                  <tr>
                    <td>{{ number }}</td>
                    <td> {{ name.first }}</td>
                    <td> {{ name.last }}</td>
                    <td>{{ name.relation }}</td>
                  </tr>
                </tbody>
               </table>
            </div>
            <div>
              <table class="table">
                <thead>
                  <tr>
                    <th>S.No</th>
                    <th>Actor Name</th>
                    <th>Actor Movie</th>
                    <th></th>
                  </tr>
                </thead>
                <tbody v-for="actor in actors" :key="actor.name">
                  <tr>
                    <td>{{ index }}</td>
                    <td>{{ actor.name }}</td>
                    <td v-for="movie in actor.movies" :key="movie">{{ movie }}</td>
                    
                  </tr>
                </tbody>
              </table>
            </div>
            <!-- <h5 v-for="(value, key, index) in myinfo" :key="value">{{index}} : {{ key }} - {{ value }}</h5> -->
          </div>
        </div>
      </div>
      <!--List Rendering ends here-->

      <!--Lists and keys starts here-->
      <div class="col col-4">
        <div class="card">
          <div class="card-header">
            <h3>Lists and keys</h3>
          </div>
          <div class="card-body">
            <div v-for="name in names" :key="name">
            <h4>{{ name }}</h4>
            <input type="text" placeholder="Last name" >
          </div>
          <button v-on:click="shuffle">Shuffle</button>
        </div>
        </div>
      </div>
      <!--Lists and keys ends here-->
      <!--Methods starts here-->
      <div class="col col-4">
        <div class="card">
          <div class="card-header">
            <h3>Methods</h3>
          </div>
          <div class="card-body">
            <h5>{{ 2 + 3 + 5 }}</h5>
            <h5>{{ 10 + 32 + 5 }}</h5>
            <h5>Add method - {{add(2,3,5) }}</h5>
            <h5>Add method - {{add(10,15,20) }}</h5>
            <h5>Multiply method - {{ multiply(baseValue) }}</h5>
        </div>
        </div>
      </div>
      <!--Methods ends here-->
      <!--event Handlers starts here-->
      <div class="col col-4">
        <div class="card">
          <div class="card-header">
            <h3>Event Handling</h3>
          </div>
          <div class="card-body">
           
      <div class="p-3">
        <h5>{{ name }}</h5>
        <button class="btn btn-primary" v-on:click="name = 'batman'">Change name on click</button>
        <button class="btn btn-secondary" v-on:mouseover="name = 'batman'">Change name on mouse over</button>
      </div>
       <div class="p-3">
        <h5>{{ count }}</h5>
        <button class="btn btn-primary" v-on:click="count += 1">Increment</button>
        <button class="btn btn-secondary" v-on:click="count -= 1">Decrement</button>
       </div>
      
        </div>
        </div>
      </div>
     
      <!--event Handlers -1 ends here-->
      <!--event Handlers - 11 starts here-->
      <div class="col col-4">
        <div class="card">
          <div class="card-header">
            <h3>Event Handling</h3>
          </div>
          <div class="card-body">
           
      <div class="p-3">
        <h5>{{ name }}</h5>
        <button class="btn btn-primary" @click="name = 'batman'">Change name on click</button>
        <button class="btn btn-secondary" @mouseover="name = 'batman'">Change name on mouse over</button>
      </div>
       <div class="p-3">
        <h5>{{ count }}</h5>
        <button class="btn btn-primary" @click="increment(1)">Increment 1</button>
        <button class="btn btn-secondary" @click="increment(5)">Increment 5</button>
        <button class="btn btn-primary" @click="decrement(1)">Decrement 1</button>
        <button class="btn btn-secondary" @click="decrement(5)">Decrement 5</button>
       </div>
      
        </div>
        </div>
      </div>
     
      <!--event Handlers ends here-->
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      channel: "codevolution",
      great: "<b>Hello</b>",
      firstname: "manjula",
      lastname: "devarala",
      hack: `<a href="#" onclick="alert('you have been hacked?')">Win a pazzle</a>`,
      headingId: 'heading',
      isDiabled: false,
      status: 'danger',
      ispromoted: true,
      isSoldOut: true,
      highlightColor: 'orange',
      headerSize: 20,
      headerStyleObject: {
        color: 'orange',
        fontSize: '20px',
      },
      baseStyleObject: {
        fontSize: '20px',
        padding: '10px'
      },
      successStyleObject: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green',
        padding: '20px'
      },
      dangerStyleObject: {
        color: 'red',
        backgroundColor: 'lightred',
        border: '1px solid red',
        padding: '20px'
      },
      num: "hi", //or num:5
      display: true,
      showElement: true,
      names: ['Bruce', 'Clark', 'Daina'],
      fullNames:[
        {first: 'Manjula', last: 'Devarala', relation:'sister'},
        {first: 'Mallesh', last: 'Devarala', relation:'brother'},
        {first: 'Maheswari', last: 'Devarala', relation:'sister'},
        {first: 'Madhavi', last: 'Devarala', relation:'sister'},
      ],
      actors:[
        {
          name:'pavan kalyan',
          movies:['Bro', 'Vakeel sab'],
        },
        {
          name:'Ritesh Deshmukh',
          movies:['Marjaavaan', 'Plan A plan B'],
        }
      ],
      myinfo:{
        name:'vignesh',
        channel:'codevolution'
      },
      names:["Jhanson", "manjula", "dudu", "chichu"],
      baseMultiplier : 5,
      baseValue: 2,
      name:'vishwas',
      count:0,
    }
  },
  methods:{
    shuffle(){
      console.log("this.name");
      this.names = _.shiffle(this.names)
    },
    add(a, b, c){
      return a + b + c
    },
    multiply(num){
      return num = this.baseMultiplier
    },
    changeName(){
      this.name = 'manjula'
    },
    increment(num){
      this.count += num
    },
    decrement(num){
      this.count -= num
    }
  }
  
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-size: 15px;
  margin-top: 60px;
}

.promoted {
  font-style: italic;
}

.soldeout {
  color: #00f;
}

.soldoutnew {
  color: #F00;
}

.new {
  color: #0f0;
}

.grid {
  display: flex;
  flex-wrap: wrap;
}

.col {
  width: calc(50% - 20px);
  margin-right: 10px;
  margin-left: 10px;
  margin-bottom: 20px;
  padding: 20px;
  background: hsl(var(--clr-dark));
  border: 1px solid #0a58ca;
  border-radius: 10px;
}

.card {
  border: 0;
  background: transparent;

}

.card-header {
  border: 0;
  background-color: #0a58ca;
  color: #fff;
}

:root {
  --clr-bg: 220 39% 15%;
  --clr-dark: 220deg 28.34% 94.87%;
  --clr-main: 0 100% 67%;
  --clr-light: 44 100% 88%;
  --clr-bright: 43 100% 65%;
  --clr-link: 199 100% 65%;
  --clr-text-base: 220 39% 95%;
}
</style>
