<template>
<div>
  <div class="hello">
    <input v-model.number="operand1"/>
    <input v-model.number="operand2"/>
	= {{result}}
  </div>
   <div class="keyboard">
         <button v-on:click="calculate('sum')">+</button>
         <button v-on:click="calculate('sub')">-</button>
         <button v-on:click="calculate('div')">/</button>
         <button v-on:click="calculate('mul')">*</button>
         <button v-on:click="calculate('exp')">a<sup>n</sup></button>
         <button v-on:click="calculate('int_div')">целочисленное /</button>
    </div>
  </div>
</template>

<script>
export default {
  
   data(){
       return {
           operand1: 0,
           operand2: 0,
           result: 0,
       }   
   },
	methods: {
		calculate (op){
			switch(op) {
				case 'sum':  this.result = this.operand1 + this.operand2;
					break;

				case 'sub':  this.result = this.operand1 - this.operand2;
					break;

				case 'div':  this.result = this.operand1 / this.operand2;
					break;

				case 'mul':  this.result = this.operand1 * this.operand2;
					break;
				
				case 'exp':  this.result = this.operand1 ** this.operand2;
					break;
				
				case 'int_div':  this.result = (this.operand1 - (this.operand1 % this.operand2)) / this.operand2;
					break;
				
				default:
					this.result = this.operand1 * this.operand2
			}
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
