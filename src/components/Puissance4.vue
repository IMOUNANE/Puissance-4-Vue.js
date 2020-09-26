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
                count:1,
                indice:["i"+1,"i"+2,"i"+3,"i"-1,"i"-2,"i"-3],
            
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
                            
                            event.srcElement.classList="cicle yellow";
                            this.tab[this.pos[0]][this.pos[2]]=1;
                            this.player=2;
                            
                        } else if (this.player==2 && memo==0){
                            event.srcElement.classList="cicle red";
                            this.tab[this.pos[0]][this.pos[2]]=2;
                            this.player=1;
                        }
                        
                        //fonction mettre les jetons en bas 

                        //fonction qui a gagné consitué de haut bas droite gauche diagonale antidiagole
                        
                 
                
                 
                 
             },
             under(){
                    //on vérifie que la position fournie est diférent de null
                    if(this.pos!== null){

                            //on vérifie si on ne sort pas du cadre, c'est à dire du haut.
                            if(parseInt(this.pos[0])-1 >= 0){
                                // on boucle trois fois pour vérifié si on a une suite de couleur.
                                for(let i=1;i<=3;i++){
                                    //memo correspond a la  couleur au dessus de la position cliqué
                                    const memo = this.tab[(this.pos[0]-i)][this.pos[2]];
                                    
                                    //on vérifie si la lal couleur au dessu corespond a celle du dessous.
                                    if(memo==this.tab[this.pos[0]][this.pos[2]])
                                    {
                                        console.log("la couleur du haut est la meme que la case choisi");
                                        //si oui on incremente
                                        this.count++;
                                        //défini quel joueur a gagner
                                        if(this.count==4){
                                            console.log(this.player-1+" a gagné");

                                        }
                                               
                                    }else{
                                        //on réinitialise le counteur de jetons de la meme couleur
                                        this.count=1;
                                        break;
                                        
                                    }
                                }
                                    
                                
                               
                                
                            }






                        
                       //if(parseInt(this.pos[0])-1 >= 0 && parseInt(this.pos[0])+1 <= 5 && parseInt(this.pos[2])+1 >= 0 && parseInt(this.pos[2])+1 <= 6 ){
                         
                        
                        
                        
                        
                        
                    
                        
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