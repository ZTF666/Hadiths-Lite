<template>
 
      <v-container class="mt-10">
        <v-row>
          <v-col>
            <v-sheet min-height="40vh" rounded="lg" >
              <v-card-text class="headline font-weight-bold text-md-center">
                <br><br><br>
                   {{RHadith}}
              </v-card-text>
              

              <div class="text-md-center mt-10 flex">
                <v-btn icon color="green"  x-large @click.prevent="RandomHadith()" >
                    <v-icon>mdi-cached</v-icon>
                </v-btn>
              </div>
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
   
</template>

<script>
export default {
  head: {
    title: 'Hadiths Lite Landing Page',
    meta: [
      {
        hid: 'Landing Page',
        name: 'Landing Page',
        content: 'Random Hadith from Al Damiri',
      },
    ],
  },
  data: () => ({
   
    api: 'https://al-damiri-hadiths-api.herokuapp.com/hadith',
    Hadiths:[],
    Hsize:'',
    RHadith:[],
    
  }),
  methods:{
    GetHadith(){
        fetch(
          `${this.api}`
        )
          .then(res => {
            return res.json();
          })
          .then(this.setResults);
    },
     setResults(results) {
     
      this.Hadiths=results
      this.Hsize=this.Hadiths.length
      
      this.RandomHadith()
     
    },
    RandomHadith(){
    let X = Math.floor((Math.random() * parseInt(this.Hsize)) + 1)
    this.RHadith=this.Hadiths[X][2]
    this.Hadiths.splice(X,1)
    this.Hsize=this.Hsize-1
    // to check if things are deleted and the size is reduced
    console.log(this.Hsize)
    console.log(this.Hadiths.length)

    }
  },
  mounted(){
    if(this.Hadiths.length<=0){
      this.GetHadith()
      console.log('everything is a-okay')}

  }
}
</script>

