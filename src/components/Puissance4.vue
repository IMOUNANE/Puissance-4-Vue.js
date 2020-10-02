<template>
<div class="calc">  

        <div class="btn">
            <div id="0:0" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn">
            <div id="0:1" class="cicle" @click="assign()"></div>
        </div>
        
        <div class="btn">
            <div id="0:2" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn">
            <div id="0:3" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn">
            <div id="0:4" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="0:5" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="0:6" class="cicle" @click="assign()"></div>
        </div>
        
        <div class="btn" >
            <div id="1:0" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="1:1" class="cicle" @click="assign()"></div>
        </div>
        <div class="btn" >
            <div id="1:2" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="1:3" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="1:4" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="1:5" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="1:6" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="2:0" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="2:1" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="2:2" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="2:3" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="2:4" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="2:5" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="2:6" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="3:0" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="3:1" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="3:2" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="3:3" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="3:4" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="3:5" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="3:6" class="cicle" @click="assign()"></div>
        </div>
        
        <div class="btn" >
            <div id="4:0" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="4:1" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="4:2" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="4:3" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="4:4" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="4:5" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="4:6" class="cicle" @click="assign()"></div>
        </div>
        <div class="btn" >
            <div id="5:0" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="5:1" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="5:2" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="5:3" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="5:4" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="5:5" class="cicle" @click="assign()"></div>
        </div>

        <div class="btn" >
            <div id="5:6" class="cicle" @click="assign()"></div>
        </div>

        
     

        
    </div>

</template>

<script>

    export default{
        data(){
            return{
                pos:[],
                player: 1,
                win:false,
                count:0,
                
                   

               
               
            
                tab:[
                        [0,0,0,0,0,0,0],
                        [0,0,0,0,0,0,0],
                        [0,0,0,0,0,0,0],
                        [0,0,0,0,0,0,0],
                        [0,0,0,0,0,0,0],
                        [0,0,0,0,0,0,0]
                    ],
               
                
            }
        },
        methods:{
            assign(){
                        
                        this.pos=event.srcElement.id.split('');
                        var memo = this.tab[this.pos[0]][this.pos[2]];
                        
                        
                        
                        if(this.player==1 && memo==0){
                            this.tab[this.pos[0]][this.pos[2]]=1;
                            this.assigncolor();
                            this.checkwinner();
                            this.player=2;
                            
                        } else if (this.player==2 && memo==0){
                            this.tab[this.pos[0]][this.pos[2]]=2;
                            this.assigncolor();
                            this.checkwinner();
                            this.player=1;
                        }
                        
                        
                        
                 
                 
            },
            checkwinner(){
                
                this.up();
                this.right();
                this.left();
                this.diagonal_right_down();
                this.diagonal_left_up();
                this.diagonal_right_up();
                this.diagonal_left_down();
                this.down();
           


                
            },
            winner(checkcolor){
                    if(checkcolor==this.player){
                        this.count++;
                        if(this.count>=4){
                        console.log("tu as gagner");
                        }
                    }
            },
            assigncolor(){
                for(let i=0 ; i<this.tab.length;i++){
                    for(let j=0 ; j<this.tab[i].length;j++){
                            
                        if(this.tab[i][j]==1){

                            
                            document.getElementById(i+this.pos[1]+j).classList="cicle yellow";
                            
                        }else if(this.tab[i][j]==2){
                            
                            document.getElementById(i+this.pos[1]+j).classList="cicle red";
                        }
                    }    
                    
                }
            },
            left(){
                    if(this.pos!== null){
                        for(let i=0;i<4;++i){
                            if((parseInt(this.pos[2])-i) >= 0){

                                var checkcolor = this.tab[(parseInt(this.pos[0]))][(parseInt(this.pos[2])-i)];
                                this.winner(checkcolor);
                            
                            }else{
                                this.count==0;
                                break;
                            }
                        }
                        this.count=0;
                    }
                  
                   
            
            },
            right(){
                    if(this.pos!== null){
                        for(let i=0;i<4;++i){
                            if((parseInt(this.pos[2])+i) <= 6){

                                var checkcolor = this.tab[(parseInt(this.pos[0]))][(parseInt(this.pos[2])+i)];
                                this.winner(checkcolor);
                               
                            }else{
                                this.count==0;
                                break;
                            }
                        }
                        this.count=0;
                    }
            },
            up(){
                    if(this.pos !== null){
                        
                        for(let i=0;i<4;++i){
                            if((parseInt(this.pos[0])-i) >= 0 ){

                                var checkcolor = this.tab[(parseInt(this.pos[0]))][(parseInt(this.pos[2])-i)];
                                this.winner(checkcolor);
                            }else{
                                this.count==0;
                                break;
                            } 
                        }
                        this.count=0;
                    }
            },
            down(){
                    if(this.pos!== null){
                        for(let i=0;i<4;++i){
                            if((parseInt(this.pos[0])+i) <= 5 ){
                                
                                var checkcolor = this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2]))];
                                this.winner(checkcolor);

                            }else{
                                this.count==0;
                                break;
                            }
                        }
                        this.count=0;
                    }
            },
            diagonal_right_down(){
                    if(this.pos!== null){
                        for(let i=0;i<4;++i){
                            if((parseInt(this.pos[0])+i) <= 5 && (parseInt(this.pos[2])+i) <=6){

                                var checkcolor = this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2])+i)];
                                this.winner(checkcolor);

                            }else{
                                this.count==0;
                                break;
                            }                        
                        }
                        this.count=0;
                    }            
            },
            diagonal_left_up(){
                    
                    if(this.pos!== null){
                        
                        for(let i=0;i<4;++i){
                            
                            if((parseInt(this.pos[0])-i) >= 0 && (parseInt(this.pos[2])-i) >=0){

                                var checkcolor = this.tab[(parseInt(this.pos[0])-i)][(parseInt(this.pos[2])-i)];
                                this.winner(checkcolor); 

                            }else{
                                this.count==0;
                                break;
                            }
                        }
                        this.count=0;
                    }   
            },
            diagonal_right_up(){
                    if(this.pos!== null){
                        
                        for(let i=0;i<4;++i){
                            
                            if((parseInt(this.pos[0])-i) >= 0 && (parseInt(this.pos[2])+i)<=6){

                                var checkcolor = this.tab[(parseInt(this.pos[0])-i)][(parseInt(this.pos[2])+i)];
                                this.winner(checkcolor);

                            }else{
                                
                                this.count==0;
                                break;
                            }
                            
                        }
                        this.count=0;
                    }  
            },
            diagonal_left_down(){
                    
                if(this.pos!== null){
                    
                    for(let i=0;i<4;++i){
                        if((parseInt(this.pos[0])+i) <= 5 && (parseInt(this.pos[2])-i) >= 0){

                            var checkcolor = this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2])-i)];
                            this.winner(checkcolor);

                        }else{
                            this.count==0;
                            break;
                        }
                    }
                    this.count=0;
                }  
            },
            
            

        }

    }

</script>
<style>
    *{
        background-color: lightblue;
        
    }
    .calc{
        width:1100px;
        height: 800px;
        margin: 0 auto;
        font-size: 50px;
        display: grid;
        grid-template-columns: repeat(7, 1fr);
        border: 20px groove blue;
        grid-auto-rows: minmax(auto,auto);
        
    }
    .cicle{
       
        width: 125px;
        height: 125px;
        background-color:lightgrey;
        border: 1px solid ;
        border-radius: 50%;
        cursor: pointer;  
    } 
    .cicle:active{
        background: white;
    } 
   .btn{
        display: flex;
        justify-content: center;
        align-items:center;
        background-color: blue;
        border: 1px solid ;
        
    }
    .yellow{
        background-color: yellow;
    }
    .red{
        background-color: red;
    }
    
</style>