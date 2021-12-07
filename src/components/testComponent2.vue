<template>
  <div class="counter">
    <textarea v-model="message" placeholder="add multiple lines"></textarea>
    <br />
    <button @click="updateData">Update</button>
    <br/>
    <span>Output:</span>
    <p style="white-space: pre-line;">{{ output }}</p>
    
  </div>
</template>

<script>

export default {
  name: 'testComponent2',
  data: function() {
    return {
      message: "",
      output: ""
    }
  },
  methods:
  {
    updateData: function () {
      
      var inputs = this.message.split('\n')
      /*inputs = [607,
618,
618,
617,
647,
716,
769,
792]*/
      var count = 0
      /*var compare1 = parseInt( inputs[0])
      var compare2 = compare1 + parseInt( inputs[1]);
      if(compare2 > compare1){
       count++;
      }
      compare1 = compare2+parseInt( inputs[2])
      if(compare1 > compare2){
       count++;
      }

*/
var compare1;
var compare2;
      for (let index = 0; index < inputs.length-3; index++) {
        const element = parseInt( inputs[index]);
        const element2 = parseInt( inputs[index+1]);
        const element3 = parseInt( inputs[index+2]);
        const elementa = parseInt( inputs[index+1]);
        const elementa2 = parseInt( inputs[index+2]);
        const elementa3 = parseInt( inputs[index+3]);
        compare1 = element + element2 + element3;
        compare2 = elementa + elementa2 + elementa3;
        if (compare2 > compare1) {
          count++
        }/*
        const elementb = parseInt( inputs[inputs.length-2]);
        const elementb2 = parseInt( inputs[inputs.length-1]);
        const elementb3 = parseInt( inputs[inputs.length]);

        compare1 = elementb + elementb2 + elementb3;
        compare2 = elementa2 + elementa3;
        if (compare2 > compare1) {
          count++
        }
        compare1 = elementb2 + elementb3;
        compare2 = elementa3;
        if (compare2 > compare1) {
          count++
        }*/
      }
this.output = count
      
    }
  },
}
</script>

