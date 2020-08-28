<template>
  <div>
    <div class="row">
      <div class="col-sm">
        <p style="font-size: 150%">{{aplayer.name}}</p>
        <p>
          <img v-bind:style="{width: aplayer.hp + 'px'}" :src="hp1" alt height="20px" />
        </p>
        <p style="font-size: 150%">{{thp}}{{aplayer.hp}}</p>
        <p>
          <img style="width:50%" :src="aplayer.image" />
        </p>
      </div>
      <!-- Botton -->
      <div class="col-sm">
        <div class="row">
          <div class="col">
            <div class="btn-group" role="group" aria-label="Basic example">
    <button v-bind:disabled="end" class="btn btn-primary" @click="start()">Start</button>
    <button v-bind:disabled="end" class="btn btn-light " @click="attack()">Attack</button>
    <button v-bind:disabled="end" class="btn btn-danger" @click="special()">Special Attack</button>
    <button class="btn btn-success" @click="reset()">Restart</button>
</div>
          </div>
          <br /> 
          <!-- VS -->
          <center><img class="rounded-circle"
            src="https://thumbs.gfycat.com/ImaginativeGrandioseArcticwolf-size_restricted.gif"
            width="80%"
          />
          </center>
         </div>
        <div class="row">
          <div class="col-sm"></div>
          <div class="col-sm">
            <div id="score">
              <!-- WIN -->
              <div v-if="amonster.hp <= 0"><img
            src="https://media3.giphy.com/media/jsGz81YPCgw9YSliV0/giphy.gif"
            width="100%"
          /></div>
              <!-- LOST -->
              <div v-else-if="aplayer.hp <= 0"><img
            src="https://lh3.googleusercontent.com/proxy/XdqGeg8FNf6nuuaVkxta-HnCPKjYUXRYhkDeRKq5ufZjGVYDujCpCL1NgiiDVGHjTJAqab6G5CUPIIuot_ROQuwRaUo_VsyC"
            width="200%"
          /></div>
            </div>
          </div>
          <div class="col-sm"></div>
        </div>
      </div>
      <div class="col-sm">
        <p style="font-size: 150%">{{amonster.name}}</p>
        <p>
          <img v-bind:style="{width: amonster.hp + 'px'}" :src="hp2" alt height="15px" />
        </p>
        <p style="font-size: 150%">{{thp}}{{amonster.hp}}</p>
        <p>
          <img style="width:50%" :src="amonster.image" />
        </p>
      </div>
    </div>
    
      
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      thp: "HP:",
      end: false,
      hp2:
        "https://img.pngio.com/health-bar-png-100-images-in-collection-page-3-health-bar-png-1200_900.png",
      hp1:
        "https://img.pngio.com/health-bar-png-pictures-trzcacakrs-health-bar-png-1190_1120.png",
      aplayer: { name: "", hp: 1, image: "", hp1: "" },
      player: [
        
        {
          name: "Iron man",
          hp: 330,
          image:
            "http://www.pngmart.com/files/3/Iron-Man-PNG-Clipart.png",
        },
        {
          name: "Spider man",
          hp: 250,
          image:
            "http://www.pngmart.com/files/1/Spiderman-Comic-PNG-HD.png",
        },
        {
          name: "Dead Pool",
          hp: 330,
          image:
            "http://www.pngmart.com/files/2/Deadpool-PNG-Photo.png",
        },
        {
          name: "Captain Marvel",
          hp: 400,
          image: "http://www.pngmart.com/files/9/Captain-Marvel-Transparent-PNG.png",
        },
        {
          name: "Captain America",
          hp: 450,
          image: "http://www.pngmart.com/files/2/Captain-America-PNG-Picture.png",
        },
        {
          name: "The Hulk",
          hp: 500,
          image:
            "http://www.pngmart.com/files/2/Hulk-Transparent-Background.png",
        },
        
         
      ],
      amonster: { name: "", hp: 1, image: "", hp1: "" },
      monster: [
        
        {
          name: "Carnage",
          hp: 500,
          image:
            "http://www.pngmart.com/files/4/Carnage-Transparent-Background.png",
        },
        {
          name: "Thanos",
          hp: 480,
          image:
            "http://www.pngmart.com/files/9/Marvel-Thanos-PNG-Transparent-Image.png",
        },
        {
          name: "Ultron",
          hp: 320,
          image: "http://www.pngmart.com/files/4/Ultron-Transparent-PNG.png",
        },
        {
          name: "Loki",
          hp: 365,
          image: "http://www.pngmart.com/files/2/Loki-Transparent-PNG.png",
        },
        {
          name: "Venom",
          hp: 500,
          image: "http://www.pngmart.com/files/4/Venom-PNG-Transparent-Image.png",
        }
      
        
      ],
      pmax: "",
      mmax: "",
    };
  },
  methods: {
    randomno: function (min, max) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    start: function () {
      this.aplayer = this.player[this.randomno(1, 7) - 1];
      this.amonster = this.monster[this.randomno(1, 7) - 1];
    },
    attack: function () {
      this.pmax = Math.floor(Math.random() * 10 + 4);
      this.amonster.hp = this.amonster.hp - this.pmax;
      this.mmax = Math.floor(Math.random() * 10 + 4);
      this.aplayer.hp = this.aplayer.hp - this.mmax;
      if (this.aplayer.hp <= 0) {
        this.aplayer.hp = 0;
        this.end = true;
      } else if (this.amonster.hp <= 0) {
        this.amonster.hp = 0;
        this.end = true;
      }
    },
    special: function () {
      this.pmax = Math.floor(Math.random() * 15 + 6);
      this.amonster.hp = this.amonster.hp - this.pmax;
      this.mmax = Math.floor(Math.random() * 15 + 6);
      this.aplayer.hp = this.aplayer.hp - this.mmax;
      if (this.aplayer.hp <= 0) {
        this.aplayer.hp = 0;
        this.end = true;
      } else if (this.amonster.hp <= 0) {
        this.amonster.hp = 0;
        this.end = true;
      }
    },
    reset: function () {
      window.location.reload();
    },
  },
};
</script>
<style>
#score {
  font-size: 300%;
  color: aliceblue;
}
</style>