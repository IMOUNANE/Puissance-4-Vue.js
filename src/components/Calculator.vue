<template>
    <div class="calc">
        <div class="display">{{ result || 0}}</div>
        <div class="btn clear" @click="clear">C</div>
        <div class="btn operator" @click="per">%</div>
        <div class="btn" @click="append(7)">7</div>
        <div class="btn" @click="append(8)">8</div>
        <div class="btn" @click="append(9)">9</div>
        <div class="btn operator" @click="divide">/</div>
        <div class="btn" @click="append(4)">4</div>
        <div class="btn" @click="append(5)">5</div>
        <div class="btn" @click="append(6)">6</div>
        <div class="btn operator" @click="multiply">x</div>
        <div class="btn" @click="append(1)">1</div>
        <div class="btn" @click="append(2)">2</div>
        <div class="btn" @click="append(3)">3</div>
        <div class="btn operator" @click="substrac">-</div>
        <div class="btn" @click="append(0)">0</div>
        <div class="btn" @click="dot">.</div>
        <div class="btn" @click="equal">=</div>
        <div class="btn operator" @click="sum" >+</div>
    </div>

</template>

<script>
    export default{
        data(){
            return{
                result:"",
                proceed: false,
                prev: null,
                operator: null,
                operatorClick: false,
            }
        },
        methods:{
            clear(){
                this.result = "";
            },
            per(){
                this.result = parseFloat(this.result)/100;
            },
            append(number){
                if(this.operatorClick){
                    this.result = "";
                    this.operatorClick = false;
                }
                this.result = this.result+number;
            },
            dot(){
                //indexOf() search params in array
                if(this.result.indexOf('.')===-1){
                    this.append('.');
                }
                /*
                    other method
                    dot(symbol)
                if(this.proceed===false){
                    this.result=this.result+symbol;
                    this.proceed=true;
                }
                */
            },
            multiply(){
                this.operator=(a,b)=>a*b;
                this.setPrev();
            },
            divide(){
                this.operator=(a,b)=> a!=0 ? b/a  : this.result = "imposible" ;
                this.setPrev();
            },
            sum(){
                this.operator=(a,b)=>a+b;
                this.setPrev();
            },
            substrac(){
                this.operator=(a,b)=>a-b;
                this.setPrev();
            },
            equal(){
                this.result=this.operator(
                    parseFloat(this.result),
                    parseFloat(this.prev)
                );
                this.prev = null;
            },
            setPrev(){
                this.prev = this.result;
                this.opperatorClick = true;
                this.result = "";
            }
            

        }

    }

</script>
<style>
    *{
        background-color: #111;
        
    }
    .calc{
        width:400px;
        margin: 0 auto;
        font-size: 50px;
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        border: 20px groove #999;
        grid-auto-rows: minmax(auto,auto);
        
    }
    .display{
        grid-column: 1/5;
        background: #333;
        color:white;
        padding:20px;
        text-align: right;
    }
    .clear{
        grid-column: 1/4;
    }    
    .btn{
        padding:10px;
        background: linear-gradient(#fafafa, lightgrey);
        border: 1px solid #999;
        cursor: pointer;
    }
    .btn:active{
        background: white;
    }
    .operator{
        color:red;
    }
</style>
