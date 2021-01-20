<template>
    <div id="app">
        <textarea name="texto" id="texto" @input="Count()" v-model="phrase" placeholder="Your text" ></textarea>
        <div>
            <span>Letters: <b>{{letters}}</b> </span>
            <span>Words: <b>{{words}}</b> </span>
            <span>Lines: <b>{{lines}}</b> </span>
        </div>
        <a href="https://github.com/Posseidon0110" target="_blank" rel="noopener noreferrer">Coded by Posseidon</a>
    </div>
</template>

<script>

export default {
    name: 'App',
    data(){
        return{
            phrase: '',
            letters: 0,
            words: 0,
            lines: 0
        }
    },
    methods: {
        Count(){
            this.letters = this.phrase.length

            if(this.phrase.trim().length == 0) {
                this.words = 0
                this.lines = 0
            }
            else{
                this.words = this.phrase.trim().split(' ').length
                this.lines = this.phrase.split("\n").length
                
                if(this.words < this.lines)this.words = this.lines
            }

        }
    } 
}
</script>

<style>
*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

html, body{
    height: 100%;
    background-color: rgb(240,240,240);
}

#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    height: 100%;
    width: 100%;
    padding: 8px;
}

textarea{
    width: 100%;
    height: 90%;
    resize: none;
    padding: 4px 8px;
    font-size: 16px;
}

textarea:focus{
    box-shadow: 0px 0px 8px 0px rgba(0,233,250,0.2);
    outline: 1px auto rgb(0, 162, 173);
}

span:nth-child(2), span:nth-child(3){
    margin-left: 16px;
}

a{
    color: rgb(75,75,75);
    text-decoration: none;
}

a:hover{
    color: rgb(0, 162, 173);
}


</style>
