
<template>

    <div class="principal">
        <div class="nueva">
            <img class="reloj" src="./imagen/alarma.gif" alt=""/>
           
            <h1>Nueva tarea:</h1>
        </div>
        <div class="g_txt">
            <input type="text" class="texto" placeholder="Nueva tarea" v-model="nombretareas">
            <button v-on:click="agregartarea"><li><img class="dedo" src="./imagen/dedos1.jpg" alt=""></li><span><b> Agregar tarea</b></span></button>
        </div>
        <div class="mensaje">
            <h5 v-if="tareas.length === 0">No hay tareas pendientes</h5>
            <hr>
        </div>
        <div class="tareas">
            
            <div class="tex2">
                <h2>Tareas pendientes</h2>
                <ul class="tareas pendientes" >
                    <div>
                        <li class="list-group-item" v-for="(tarea,index) in tareas" v-bind:key="index" >
                        {{tarea.nombretareas}}
                        <span class="cursor">
                            <i><img class="img" src="./imagen/verif.png" alt=""></i>
                        </span>
                        <span class="cursor" v-on:click="eliminartarea(index)">
                            <i><img class="img" src="./imagen/error.png" alt=""></i>
                        </span>
                    </li>

                    </div>
                  
                </ul>
            </div>
            <div class="tex2">
                <h2>Tareas terminadas</h2>
                <ul class="tareas terminadas">
                    <li></li>
                </ul>
                
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            tareas:[],
            nombretareas:''
        }
    },
    methods: {
        agregartarea(){
            const tarea={
                nombretareas:this.nombretareas,
                estado:false
            }
            this.tareas.push(tarea);
            this.nombretareas='';
            console.log(this.tareas)
        },
        eliminartarea(index){
            
            if (confirm('¿Seguro que quieres eliminar?')){
                this.tareas.splice(index,1) 
            }
        }
    },
  

}
</script>


<style scoped>
.principal{
    height: 100%;
    border-radius: 15px;
    background-image: url('./imagen/qq.jpg');
    background-size: cover;
    background-repeat: no-repeat;
    background-attachment: local;
    background-position: center;
}
.img{
    height: 20px;
    margin: 10px;
}
.cursor{
    cursor: pointer;
}
.tareas{
    margin: auto;
    margin-top: 30px;
    width: 90%;
    height: 60%;
    text-align: center;
    display: flex;
 
}
.list-group-item{
    text-align: left;
    list-style-type: no;
    background-color: white;
    margin-top: 10px;
    border-radius: 10px;
    padding-left: 10px;
}
hr{
    border: 1px solid black;
}
/**/

.reloj{
    height: 55px;
    padding-top: 10px;
}
h1{
    margin-top: 8px;
    font-size: 35px;
    padding-left: 5px;
    font-weight: 800;
    filter: drop-shadow(0 2px 5px rgba(0, 0, 0, 0.7));
    font-style: unset;
    font-family: "Comic Sans MS", cursive, sans-serif;
    text-shadow: rgb(196, 42, 176) -1px 1px, rgb(165, 24, 153) -2px 2px, rgb(167, 22, 148) -3px 3px, rgb(139, 20, 113) -4px 4px, rgb(139, 20, 139) -5px 5px;
    color: rgb(18, 3, 32);
    letter-spacing: 1px;
    
}
h5{
    text-align: center;
    font-size: 28px;
    filter: drop-shadow(0 2px 5px rgba(15, 15, 14, 0.7));
    font-style: unset;
    font-family: "Comic Sans MS", cursive, sans-serif;
    font-weight: 900;
    text-shadow: rgb(196, 42, 188) -1px 1px, rgb(165, 24, 158) -2px 2px, rgb(167, 22, 155) -3px 3px, rgb(139, 20, 119) -4px 4px, rgb(139, 20, 133) -5px 5px;
    color: rgb(18, 3, 32);
    letter-spacing: 1px;
}

.nueva{
    display: flex;
    margin-left: 20px;
}
li{
    list-style-type: none;
}
button{
    display: flex;
    margin-left: 10px;
    filter: drop-shadow(0 2px 5px rgba(0, 0, 0, 0.7));
    background-color: rgb(240, 159, 240);
}
.dedo{
    height: 20px;
}
.texto{
    width: 50%;
    filter: drop-shadow(0 2px 5px rgba(0, 0, 0, 0.7));
    background-color: rgb(240, 159, 240);
}
.tex2{
    height: 40%;
    width: 65%;
}
.g_txt{
    display: flex;
    margin-left: 15px;
}
span{
    padding-top: 5px;
    padding-left: 5px;
}
/**/



h2{
  
  
    filter: drop-shadow(0 2px 5px rgba(15, 15, 14, 0.7));
    font-size: 28px;
    font-style: unset;
    font-family: "Comic Sans MS", cursive, sans-serif;
    font-weight: 900;
    text-shadow: rgb(196, 42, 188) -1px 1px, rgb(165, 24, 158) -2px 2px, rgb(167, 22, 155) -3px 3px, rgb(139, 20, 119) -4px 4px, rgb(139, 20, 133) -5px 5px;
    color: rgb(18, 3, 32);
    letter-spacing: 1px;
}
/**/


</style>
