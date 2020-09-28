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
                            
                            event.srcElement.classList="cicle yellow";
                            //this.tab[this.pos[0]][this.pos[2]]=1;
                            this.gravity();
                            this.winner();
                            this.player=2;
                            
                        } else if (this.player==2 && memo==0){
                            event.srcElement.classList="cicle red";
                            this.gravity();
                            this.winner();
                            this.player=1;
                        }
                        
                        //fonction mettre les jetons en bas 

                        //fonction qui a gagné consitué de haut bas droite gauche diagonale antidiagole
                        
                        //this.down();
                        //this.under();
                        //this.diagonal_left_up();
                        
                 
                 
            },
            winner(){
                
               
                this.up(this.player);
                this.right(this.player);
                this.left(this.player);
                this.diagonal_right_down(this.player);
                this.diagonal_left_up(this.player);
                this.diagonal_right_up(this.player);
                this.diagonal_left_down(this.player);
                this.down(this.player);
                
            },
            gravity(){
                if(this.pos !== null){
                    
                    var number = 6 - parseInt(this.pos[0]);
                    for(let i=1 ; i < number ; i++){
                        console.log(i);
                        //console.log(this.tab[(parseInt(this.pos[0])-i)][parseInt(this.pos[2])]);
                        if((parseInt(this.pos[0])+i <= 5)){
                            //console.log(this.pos[0]+i);
                            console.log(this.pos[0]);
                            console.log(this.tab[(parseInt(this.pos[0])+i)][parseInt(this.pos[2])]);
                            console.log("la position a vérifié est "+(parseInt(this.pos[0])+i) +":"+parseInt(this.pos[2])+'est sa couleur est '+this.tab[(parseInt(this.pos[0])+i)][parseInt(this.pos[2])]);
                            console.log(this.tab);
                            if(this.tab[(parseInt(this.pos[0])+i)][parseInt(this.pos[2])]==0){
                                console.log("case vide");
                            }
                            else{
                                console.log("la case n'est pas vide");
                                this.pos[0]=parseInt(this.pos[0])- number;
                                this.tab[this.pos[0]][this.pos[2]]=this.player;
                                break;
                            }
                        }else{
                            console.log("hors cadre");
                            break;
                        }
                    }
                }
            },
            left(player=this.player){
                    //on vérifie que la position fournie est différent de null
                    if(this.pos!== null){
                        //on itère afin de trouvé une suite de meme couleur en direction de right_down
                        for(let i=0;i<4;++i){
                            //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i)); 
                            //console.log("compris dans la verticale: "+((parseInt(this.pos[0])+i)<= 5));
                            //console.log("compris dans l'honrizontal: "+((parseInt(this.pos[2])+i) <=6));
                            //console.log(" test la condition")
                            //console.log((parseInt(this.pos[0])+i)+ ' : ' + (parseInt(this.pos[2])+i) );
                            //on vérifie si on ne sort pas du cadre.
                            if((parseInt(this.pos[2])+i) >= 0){

                                //console.log("la position a vérifié est dans le cadre");
                                //on cible la couleur du joueur
                                //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i));
                                //console.log("la couleur de la position à vérifier est "+this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2])+i)]);
                                var checkcolor = this.tab[(parseInt(this.pos[0]))][(parseInt(this.pos[2])-i)];
                                //var colorpos = this.tab[parseInt(this.pos[0])][parseInt(this.pos[2])];
                                
                                
                                //console.log( checkcolor);
                                //console.log(colorpos);
                                //console.log(this.player);
                                //console.log(colorpos);

                                if(checkcolor==player){
                                    //console.log("le joueur 1 et les deux pions ils ont la meme couleur");
                                    //console.log("le compteur est a "+this.count+" avant incrémentation");
                                    this.count++;
                                    //console.log("le compteur est a "+this.count+" après incrémentation");
                                    if(this.count>=4){
                                    console.log("tu as gagner");
                                    }
                                }  
                            }else{
                                //console.log("la position n'est pas dans le cadre");
                                this.count==0;
                                break;
                            }
                            //console.log(i);
                            //console.log("la position à vérifié est "+parseInt(this.pos[0]+(i+1))+" : "+parseInt(this.pos[2]));
                        
                        }
                        this.count=0;
                        //console.log ("on réinitialise le count a "+this.count+" car pas de suite");
                    }
                  
                   
            
            },
            right(player=this.player){
                    //on vérifie que la position fournie est différent de null
                    if(this.pos!== null){
                        //on itère afin de trouvé une suite de meme couleur en direction de right_down
                        for(let i=0;i<4;++i){
                            //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i)); 
                            //console.log("compris dans la verticale: "+((parseInt(this.pos[0])+i)<= 5));
                            //console.log("compris dans l'honrizontal: "+((parseInt(this.pos[2])+i) <=6));
                            //console.log(" test la condition")
                            //console.log((parseInt(this.pos[0])+i)+ ' : ' + (parseInt(this.pos[2])+i) );
                            //on vérifie si on ne sort pas du cadre.
                            if((parseInt(this.pos[2])+i) <= 6){

                                //console.log("la position a vérifié est dans le cadre");
                                //on cible la couleur du joueur
                                //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i));
                                //console.log("la couleur de la position à vérifier est "+this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2])+i)]);
                                var checkcolor = this.tab[(parseInt(this.pos[0]))][(parseInt(this.pos[2])+i)];
                                //var colorpos = this.tab[parseInt(this.pos[0])][parseInt(this.pos[2])];
                                
                                
                                //console.log( checkcolor);
                                //console.log(colorpos);
                                //console.log(this.player);
                                //console.log(colorpos);

                                if(checkcolor==player){
                                    //console.log("le joueur 1 et les deux pions ils ont la meme couleur");
                                    //console.log("le compteur est a "+this.count+" avant incrémentation");
                                    this.count++;
                                    //console.log("le compteur est a "+this.count+" après incrémentation");
                                    if(this.count>=4){
                                    console.log("tu as gagner");
                                    }
                                }  
                            }else{
                                //console.log("la position n'est pas dans le cadre");
                                this.count==0;
                                break;
                            }
                            //console.log(i);
                            //console.log("la position à vérifié est "+parseInt(this.pos[0]+(i+1))+" : "+parseInt(this.pos[2]));
                        
                        }
                        this.count=0;
                        //console.log ("on réinitialise le count a "+this.count+" car pas de suite");
                    }
                  
                   
            
            },
            up(player=this.player){
                    //on vérifie que la position fournie est différent de null
                    if(this.pos !== null){
                        //on itère afin de trouvé une suite de meme couleur en direction de right_down
                        for(let i=0;i<4;++i){
                            //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i)); 
                            //console.log("compris dans la verticale: "+((parseInt(this.pos[0])+i)<= 5));
                            //console.log("compris dans l'honrizontal: "+((parseInt(this.pos[2])+i) <=6));
                            //console.log(" test la condition")
                            //console.log((parseInt(this.pos[0])+i)+ ' : ' + (parseInt(this.pos[2])+i) );
                            //on vérifie si on ne sort pas du cadre.
                            if((parseInt(this.pos[0])-i) >= 0 ){

                                //console.log("la position a vérifié est dans le cadre");
                                //on cible la couleur du joueur
                                //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i));
                                //console.log("la couleur de la position à vérifier est "+this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2])+i)]);
                                var checkcolor = this.tab[(parseInt(this.pos[0]))][(parseInt(this.pos[2])-i)];
                                //var colorpos = this.tab[parseInt(this.pos[0])][parseInt(this.pos[2])];
                                
                                
                                //console.log( checkcolor);
                                //console.log(colorpos);
                                //console.log(this.player);
                                //console.log(colorpos);

                                if(checkcolor==player){
                                    //console.log("le joueur 1 et les deux pions ils ont la meme couleur");
                                    //console.log("le compteur est a "+this.count+" avant incrémentation");
                                    this.count++;
                                    //console.log("le compteur est a "+this.count+" après incrémentation");
                                    if(this.count>=4){
                                    console.log("tu as gagner");
                                    }
                                }  
                            }else{
                                //console.log("la position n'est pas dans le cadre");
                                this.count==0;
                                break;
                            }
                            //console.log(i);
                            //console.log("la position à vérifié est "+parseInt(this.pos[0]+(i+1))+" : "+parseInt(this.pos[2]));
                        
                        }
                        this.count=0;
                        //console.log ("on réinitialise le count a "+this.count+" car pas de suite");
                    }
                  
                   
            
            },
            down(player=this.player){
                    //on vérifie que la position fournie est différent de null
                    if(this.pos!== null){
                        //on itère afin de trouvé une suite de meme couleur en direction de right_down
                        for(let i=0;i<4;++i){
                            //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i)); 
                            //console.log("compris dans la verticale: "+((parseInt(this.pos[0])+i)<= 5));
                            //console.log("compris dans l'honrizontal: "+((parseInt(this.pos[2])+i) <=6));
                            //console.log(" test la condition")
                            //console.log((parseInt(this.pos[0])+i)+ ' : ' + (parseInt(this.pos[2])+i) );
                            //on vérifie si on ne sort pas du cadre.
                            if((parseInt(this.pos[0])+i) <= 5 ){

                                //console.log("la position a vérifié est dans le cadre");
                                //on cible la couleur du joueur
                                //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])));
                                //console.log("la couleur de la position à vérifier est "+this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2]))]);
                                var checkcolor = this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2]))];
                                //console.log(checkcolor);
                                //var colorpos = this.tab[parseInt(this.pos[0])][parseInt(this.pos[2])];
                                
                                
                                //console.log( checkcolor);
                                //console.log(colorpos);
                                //console.log(this.player);
                                //console.log(colorpos);

                                if(checkcolor==player){
                                    //console.log("le joueur 1 et les deux pions ils ont la meme couleur");
                                    //console.log("le compteur est a "+this.count+" avant incrémentation");
                                    this.count++;
                                    //console.log("le compteur est a "+this.count+" après incrémentation");
                                    if(this.count>=4){
                                    console.log("tu as gagner");
                                    }
                                }  
                            }else{
                                //console.log("la position n'est pas dans le cadre");
                                this.count==0;
                                break;
                            }
                            //console.log(i);
                            //console.log("la position à vérifié est "+parseInt(this.pos[0]+(i+1))+" : "+parseInt(this.pos[2]));
                        
                        }
                        this.count=0;
                        //console.log ("on réinitialise le count a "+this.count+" car pas de suite");
                    }
                  
                   
            
            },
            diagonal_right_down(player=this.player){
                    //on vérifie que la position fournie est différent de null
                    if(this.pos!== null){
                        //on itère afin de trouvé une suite de meme couleur en direction de right_down
                        for(let i=0;i<4;++i){
                            //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i)); 
                            //console.log("compris dans la verticale: "+((parseInt(this.pos[0])+i)<= 5));
                            //console.log("compris dans l'honrizontal: "+((parseInt(this.pos[2])+i) <=6));
                            //console.log(" test la condition")
                            //console.log((parseInt(this.pos[0])+i)+ ' : ' + (parseInt(this.pos[2])+i) );
                            //on vérifie si on ne sort pas du cadre.
                            if((parseInt(this.pos[0])+i) <= 5 && (parseInt(this.pos[2])+i) <=6){

                                //console.log("la position a vérifié est dans le cadre");
                                //on cible la couleur du joueur
                                //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i));
                                //console.log("la couleur de la position à vérifier est "+this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2])+i)]);
                                var checkcolor = this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2])+i)];
                                //var colorpos = this.tab[parseInt(this.pos[0])][parseInt(this.pos[2])];
                                
                                
                                //console.log( checkcolor);
                                //console.log(colorpos);
                                //console.log(this.player);
                                //console.log(colorpos);

                                if(checkcolor==player){
                                    //console.log("le joueur 1 et les deux pions ils ont la meme couleur");
                                    //console.log("le compteur est a "+this.count+" avant incrémentation");
                                    this.count++;
                                    //console.log("le compteur est a "+this.count+" après incrémentation");
                                    if(this.count>=4){
                                    console.log("tu as gagner");
                                    }
                                }  
                            }else{
                                //console.log("la position n'est pas dans le cadre");
                                this.count==0;
                                break;
                            }
                            //console.log(i);
                            //console.log("la position à vérifié est "+parseInt(this.pos[0]+(i+1))+" : "+parseInt(this.pos[2]));
                        
                        }
                        this.count=0;
                        //console.log ("on réinitialise le count a "+this.count+" car pas de suite");
                    }
                  
                   
            
            },
            diagonal_left_up(player=this.player){
                    //on vérifie que la position fournie est différent de null
                    if(this.pos!== null){
                        //on itère afin de trouvé une suite de meme couleur en direction de right_down
                        for(let i=0;i<4;++i){
                            //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i)); 
                            //console.log("compris dans la verticale: "+((parseInt(this.pos[0])+i)<= 5));
                            //console.log("compris dans l'honrizontal: "+((parseInt(this.pos[2])+i) <=6));
                            //console.log(" test la condition")
                            //console.log((parseInt(this.pos[0])+i)+ ' : ' + (parseInt(this.pos[2])+i) );
                            //on vérifie si on ne sort pas du cadre.
                            if((parseInt(this.pos[0])-i) >= 0 && (parseInt(this.pos[2])-i) >=0){

                                //console.log("la position a vérifié est dans le cadre");
                                //on cible la couleur du joueur
                                //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i));
                                //console.log("la couleur de la position à vérifier est "+this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2])+i)]);
                                var checkcolor = this.tab[(parseInt(this.pos[0])-i)][(parseInt(this.pos[2])-i)];
                                //var colorpos = this.tab[parseInt(this.pos[0])][parseInt(this.pos[2])];
                                
                                
                                //console.log( checkcolor);
                                //console.log(colorpos);
                                //console.log(this.player);
                                //console.log(colorpos);

                                if(checkcolor==player){
                                    //console.log("le joueur 1 et les deux pions ils ont la meme couleur");
                                    //console.log("le compteur est a "+this.count+" avant incrémentation");
                                    this.count++;
                                    //console.log("le compteur est a "+this.count+" après incrémentation");
                                    if(this.count>=4){
                                    console.log("tu as gagner");
                                    }
                                }  
                            }else{
                                //console.log("la position n'est pas dans le cadre");
                                this.count==0;
                                break;
                            }
                            //console.log(i);
                            //console.log("la position à vérifié est "+parseInt(this.pos[0]+(i+1))+" : "+parseInt(this.pos[2]));
                        
                        }
                        this.count=0;
                        //console.log ("on réinitialise le count a "+this.count+" car pas de suite");
                    }
                  
                   
            
            },
            diagonal_right_up(player=this.player){
                    //on vérifie que la position fournie est différent de null
                    if(this.pos!== null){
                        //on itère afin de trouvé une suite de meme couleur en direction de right_down
                        for(let i=0;i<4;++i){
                            //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i)); 
                            //console.log("compris dans la verticale: "+((parseInt(this.pos[0])+i)<= 5));
                            //console.log("compris dans l'honrizontal: "+((parseInt(this.pos[2])+i) <=6));
                            //console.log(" test la condition")
                            //console.log((parseInt(this.pos[0])+i)+ ' : ' + (parseInt(this.pos[2])+i) );
                            //on vérifie si on ne sort pas du cadre.
                            if((parseInt(this.pos[0])-i) >= 0 && (parseInt(this.pos[2])+i)<=6){

                                //console.log("la position a vérifié est dans le cadre");
                                //on cible la couleur du joueur
                                //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i));
                                //console.log("la couleur de la position à vérifier est "+this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2])+i)]);
                                var checkcolor = this.tab[(parseInt(this.pos[0])-i)][(parseInt(this.pos[2])+i)];
                                //var colorpos = this.tab[parseInt(this.pos[0])][parseInt(this.pos[2])];
                                
                                
                                //console.log( checkcolor);
                                //console.log(colorpos);
                                //console.log(this.player);
                                //console.log(colorpos);

                                if(checkcolor==player){
                                    //console.log("le joueur 1 et les deux pions ils ont la meme couleur");
                                    //console.log("le compteur est a "+this.count+" avant incrémentation");
                                    this.count++;
                                    //console.log("le compteur est a "+this.count+" après incrémentation");
                                    if(this.count>=4){
                                    console.log("tu as gagner");
                                    }
                                }  
                            }else{
                                //console.log("la position n'est pas dans le cadre");
                                this.count==0;
                                break;
                            }
                            //console.log(i);
                            //console.log("la position à vérifié est "+parseInt(this.pos[0]+(i+1))+" : "+parseInt(this.pos[2]));
                        
                        }
                        this.count=0;
                        //console.log ("on réinitialise le count a "+this.count+" car pas de suite");
                    }
                  
                   
            
            },
            diagonal_left_down(player=this.player){
                    //on vérifie que la position fournie est différent de null
                    if(this.pos!== null){
                        //on itère afin de trouvé une suite de meme couleur en direction de right_down
                        for(let i=0;i<4;++i){
                            //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i)); 
                            //console.log("compris dans la verticale: "+((parseInt(this.pos[0])+i)<= 5));
                            //console.log("compris dans l'honrizontal: "+((parseInt(this.pos[2])+i) <=6));
                            //console.log(" test la condition")
                            //console.log((parseInt(this.pos[0])+i)+ ' : ' + (parseInt(this.pos[2])+i) );
                            //on vérifie si on ne sort pas du cadre.
                            if((parseInt(this.pos[0])+i) <= 5 && (parseInt(this.pos[2])-i) >= 0){

                                //console.log("la position a vérifié est dans le cadre");
                                //on cible la couleur du joueur
                                //console.log("la position a vérifié est "+(parseInt(this.pos[0])+i)+" : "+(parseInt(this.pos[2])+i));
                                //console.log("la couleur de la position à vérifier est "+this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2])+i)]);
                                var checkcolor = this.tab[(parseInt(this.pos[0])+i)][(parseInt(this.pos[2])-i)];
                                //var colorpos = this.tab[parseInt(this.pos[0])][parseInt(this.pos[2])];
                                
                                
                                //console.log( checkcolor);
                                //console.log(colorpos);
                                //console.log(this.player);
                                //console.log(colorpos);

                                if(checkcolor==player){
                                    //console.log("le joueur 1 et les deux pions ils ont la meme couleur");
                                    //console.log("le compteur est a "+this.count+" avant incrémentation");
                                    this.count++;
                                    //console.log("le compteur est a "+this.count+" après incrémentation");
                                    if(this.count>=4){
                                    console.log("tu as gagner");
                                    }
                                }  
                            }else{
                                //console.log("la position n'est pas dans le cadre");
                                this.count==0;
                                break;
                            }
                            //console.log(i);
                            //console.log("la position à vérifié est "+parseInt(this.pos[0]+(i+1))+" : "+parseInt(this.pos[2]));
                        
                        }
                        this.count=0;
                        //console.log ("on réinitialise le count a "+this.count+" car pas de suite");
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