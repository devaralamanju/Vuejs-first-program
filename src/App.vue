<template>
  <form @submit.prevent="submitForm">
    <div>
    <pre>
      {{ JSON.stringify(formValues, null, 2) }}
    </pre>
  </div>
    <div class="form-group">
      <label for="name"><b>Name</b></label>
      <input class="form-control" type="text" v-model.trim.lazy="formValues.name" id="name">
  </div>

  <div class="form-group">
    <label for="profile"><b>Profile summary</b></label>
    <textarea name="" id="profile" class="w-100" v-model="formValues.profileSummary"></textarea>
  </div>

  <div class="form-group">
    <label for="Country"><b>Country</b></label>
    <select class="form-control" name="" id="country" v-model="formValues.country">
      <option value="">Select a country</option>
      <option value="India">India</option>
      <option value="vietnam">vietnam</option>
      <option value="singapore">India</option>
    </select>
  </div>
  <div class="form-group">
    <label for="job-location"><b>Job Location</b></label>
    <select class="form-control" name="" id="job-location" multiple v-model="formValues.jobLocation">
      <option value="">Select a country</option>
      <option value="India">India</option>
      <option value="vietnam">vietnam</option>
      <option value="singapore">India</option>
    </select>
  </div>
  <div class="form-check">
    <input type="checkbox" class="form-check-input" id="remotework" v-model="formValues.remoteWork" true-value="yes" false-value="no"/>
    <label class="form-check-label" for="remotework ">Open to remote Work?</label>
  </div>
<div>
  <label for="">Skill Set</label>
  <input type="checkbox" id="html" value="html" v-model="formValues.skillSet">
  <label for="">html</label>
  <input type="checkbox" id="css" value="css" v-model="formValues.skillSet">
  <label for="css">CSS</label>
  <input type="checkbox" id="javascript" value="javascript" v-model="formValues.skillSet">
  <label for="javascript">Javascript</label>
</div>

<div>
  <label>Years of Experice</label>
  <br/>
  <input 
  type="radio"
  id="0-2"
  value="0-2"
  v-model="formValues.yearOfExperince"
  />
  <label for="0-2">0-2</label>
  <input
  type="radio"
  id="3-5"
  value="3-5"
  v-model="formValues.yearOfExperince"
  />
  <label for="3-5">1-10</label>
  <input 
  type="radio"
  id="6-10"
  value="6-10"
  v-model="formValues.yearOfExperince"
  />
  <label for="6-10">5-10</label>
  <input 
  type="radio"
  id="10+"
  value="10+"
  v-model="formValues.yearOfExperince"
  />
  <label for="10+">10+</label>
  </div>

  <div>
  <label for="age">Age</label>
  <input @keyup.enter="submitForm" type="number" id="age" v-model.number="formValues.age" />
</div>

  <!-- <div>
  <button class="btn btn-primary">Submit</button>
</div> -->


</form>


    
</template>
<script>
export default {
  name: 'App',
  data(){
    return{
      formValues:{
        name: '',
        profileSummary:'',
        country:'',
        jobLocation:'',
        remoteWork:'no',
        skillSet: [],
        yearOfExperince:'',
        age:null, 
      }
    }
  },
  methods:{
    submitForm(){
      // event.preventDefault()
      console.log('Form values', this.formValues)
    }
  }
}
</script>
<style lang="">

</style>
