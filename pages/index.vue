<template>
  <div  class="content countdown-timer">
    <video
      ref="myvid"
      src="vid.mp4"
      preload="auto"
      playsinline
      webkit-playsinline
    >
    </video>
    <div class="playpause" @click="playit" ref="playbut"></div>


  </div>
</template>

<style >
video {
  /* override other styles to make responsive */
  width: 100%    !important;
  height: auto   !important;
}

.playpause {
    background-image:url(http://png-4.findicons.com/files/icons/2315/default_icon/256/media_play_pause_resume.png);
    background-repeat:no-repeat;
    width:50%;
    height:50%;
    position:absolute;
    left:0%;
    right:0%;
    top:0%;
    bottom:0%;
    margin:auto;
    background-size:contain;
    background-position: center;
}

</style>

<script>
  export default {
    data() {
    return {
        myvid: ""
    }
  },
  created() {
    var pass = ""
    var options = ["🌴🌴🌴🌴", "את יודעת את זה 🌴", "👉🌴🌴👈"]
    pass = prompt("סיסמא", "מה הסיסמא?");
    while (pass != "עצים") {
      var rand = Math.floor(Math.random() * options.length);
      pass = prompt(options[rand], "");
    }
  },
  methods: {
    playit: function() {
      this.$refs.myvid.play()
      this.$refs.playbut.style.display = 'none'
    }

  }

  }
</script>
