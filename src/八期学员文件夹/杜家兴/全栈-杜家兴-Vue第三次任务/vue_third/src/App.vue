<template>
  <div>
    <artist>
      <template v-slot:artist>
        <div class="photo">
          <span v-for="(pic, index) in artist" :key="index">
            <img :src="pic.picUrl" class="one">
            <div class="name">{{ pic.name }}</div>
          </span>
        </div>
      </template>
    </artist>

    <song>
      <template v-slot:hotSong>
        <div class="title">
          <span>
            <span>
              <h2>{{ hotSong.name }}</h2>
              <div class="description">{{ hotSong.description }}</div>
            </span>
            <img :src="hotSong.coverImgUrl" class="two">
            <div class="hr"></div>
          </span>
        </div>
        <div>
          <div class="show" v-for="(song, index) in hotSong.tracks" :key="index">{{ ++index }} -- {{ song.name }}</div>
        </div>
      </template>
      <template v-slot:newSong>
        <div class="title">
          <span>
            <span>
              <h2>{{ newSong.name }}</h2>
              <div class="description">{{ newSong.description }}</div>
            </span>
            <img :src="newSong.coverImgUrl" class="two">
            <div class="hr"></div>
          </span>
        </div>
        <div>
          <div class="show" v-for="(song, index) in newSong.tracks" :key="index">{{ ++index }} -- {{ song.name }}</div>
        </div>
      </template>
      <template v-slot:originSong>
        <div class="title">
          <span>
            <span>
              <h2>{{ originSong.name }}</h2>
              <div class="description">{{ originSong.description }}</div>
            </span>
            <img :src="originSong.coverImgUrl" class="two Two">
            <div class="hr Two"></div>
          </span>
        </div>
        <div>
          <div class="show TWO" v-for="(song, index) in originSong.tracks" :key="index">{{ ++index }} -- {{ song.name }}</div>
        </div>
      </template>
    </song>
  </div>
</template>

<script>
import artist from './components/artist.vue'
import song from './components/song.vue'
export default {
  name: 'App',
  components: {
    artist,
    song
  },
  data() {
    return {
      artist: [
        {
          name: "林俊杰",
          picUrl:
            "http://p1.music.126.net/78q0jUUJ0h08GxAs2G-tCA==/109951168529051968.jpg",
          altUrl:
            "http://p1.music.126.net/r6W-zCnV-aduVn_PLZYuYg==/109951168529049969.jpg",
        },
        {
          name: "薛之谦",
          picUrl:
            "http://p1.music.126.net/LCWqYYKoCEZKuAC3S3lIeg==/109951165034938865.jpg",
          altUrl:
            "http://p1.music.126.net/1tSJODTpcbZvNTCdsn4RYA==/109951165034950656.jpg",
        },
        {
          name: "陈奕迅",
          picUrl:
            "http://p1.music.126.net/w_vuv9hBWq2hlJxJcmJrjg==/109951166115915081.jpg",
          altUrl:
            "http://p1.music.126.net/rYYhHXZHwCfizE0N46F37Q==/109951166115911716.jpg",
        },
        {
          name: "邓紫棋",
          picUrl:
            "http://p1.music.126.net/fq1O8ZRT5_FHzg_uLEtUQA==/109951167773880633.jpg",
          altUrl:
            "http://p1.music.126.net/oJorrgJ3IotZUAbZkBMuFw==/109951167771736533.jpg",
        },
        {
          name: "李荣浩",
          picUrl:
            "http://p1.music.126.net/mkWDxcXZk8W3NwdCEMg00A==/109951165693668650.jpg",
          altUrl:
            "http://p1.music.126.net/MST3f1Uv77SwFyTf0Gcj5w==/109951168324499292.jpg",
        },
        {
          name: "告五人",
          picUrl:
            "http://p1.music.126.net/Xyoa72EqbaHGHiSfL5D_qA==/109951168306629780.jpg",
          altUrl:
            "http://p1.music.126.net/MbhzNEtk-c3KybdGtq3ueQ==/109951168306621485.jpg",
        },
        {
          name: "周杰伦",
          picUrl:
            "http://p1.music.126.net/BbR3TuhPULMLDV0MjczI4g==/109951165793869641.jpg",
          altUrl:
            "http://p1.music.126.net/Esjm32Q05PQoX8pF008u7w==/109951165793871057.jpg",
        },
        {
          name: "毛不易",
          picUrl:
            "http://p1.music.126.net/W5LXS0-I-P9Wk6lQpS6HGA==/109951165787072463.jpg",
          altUrl:
            "http://p1.music.126.net/3L4q_THtqVP0Tuofry303Q==/109951168543731054.jpg",
        },
        {
          name: "张杰",
          picUrl:
            "http://p1.music.126.net/-Of37SoslyjWsPhLKTogqQ==/109951168167006631.jpg",
          altUrl:
            "http://p1.music.126.net/z2HqHy_CXghF0ehV-CzL9g==/109951168234197887.jpg",
        },
        {
          name: "许嵩",
          picUrl:
            "http://p1.music.126.net/_D9P0JKRDYm3jEay9EfhRw==/109951163536274581.jpg",
          altUrl:
            "http://p1.music.126.net/ATZ8-mOxophKXrLC0iXMZw==/109951163536269820.jpg",
        },
      ],

      hotSong: {
        name: "热歌榜",
        coverImgUrl: "https://p1.music.126.net/ZyUjc7K_GDpD8MO1-GQkmA==/109951166952706664.jpg",
        description: "云音乐热歌榜：云音乐用户一周内收听所有线上歌曲官方TOP排行榜，每日更新。",
        tracks: [
          {
            name: "雪 Distance",
            picUrl: "http://p3.music.126.net/cGTKkFl5qcXIDYPo7PrmDA==/109951168431655039.jpg",
          },
          {
            name: "我记得",
            picUrl: "http://p4.music.126.net/FCWD6ibS2JK2B3QAnXuzwQ==/109951167805892385.jpg",
          },
          {
            name: "把回忆拼好给你",
            picUrl: "http://p4.music.126.net/CBx2K_jEN3SNWwYztagPPw==/109951164485969446.jpg",
          },
          {
            name: "精卫",
            picUrl: "http://p3.music.126.net/jSH_ikeooxveWl0BTc3Xkg==/109951166786983190.jpg",
          },
          {
            name: "姑娘在远方",
            picUrl: "http://p4.music.126.net/69MfQfl-rA0IwEuRSCEyNw==/109951168307420773.jpg",
          },
          {
            name: "我的美丽feat.海洋Bo",
            picUrl: "http://p4.music.126.net/8ZpCzo4gEeCAQyXAGYXKUQ==/109951167854450663.jpg",
          },
          {
            name: "可能",
            picUrl: "http://p3.music.126.net/Lk26KqRDPVbbhB4rQRGnPw==/109951167570919875.jpg",
          },
          {
            name: "在你的身边",
            picUrl: "http://p3.music.126.net/AYNBdRxJ8EdZo4xFjp7b4Q==/109951163191178425.jpg",
          },
          {
            name: "若把你",
            picUrl: "http://p3.music.126.net/M877M2-VhWZiLPVFORf9iQ==/109951163401482434.jpg",
          },
          {
            name: "唯一",
            picUrl: "http://p4.music.126.net/5URIeP6GjMFg_hKhGloNTA==/109951165585701063.jpg",
          },
        ],
      },

      newSong: {
        name: "新歌榜",
        coverImgUrl: "https://p1.music.126.net/wVmyNS6b_0Nn-y6AX8UbpQ==/109951166952686384.jpg",
        description: "云音乐新歌榜：云音乐用户一周内收听所有新歌（一月内最新发行） 官方TOP排行榜，每天更新。",  
        tracks: [
          {
            name: "アイドル",
            picUrl: "http://p3.music.126.net/4EQzPt4OaZraiSCRGpINwQ==/109951168506561762.jpg",
          },
          {
            name: "声音",
            picUrl: "http://p3.music.126.net/eble6u8GXivcHyZ9PS6P0w==/109951168475709963.jpg",
          },
          {
            name: "身骑白马",
            picUrl: "http://p3.music.126.net/iEdL_IAsaIRwNX10HtNsGg==/109951168540070885.jpg",
          },
          {
            name: "明天",
            picUrl: "http://p3.music.126.net/rYPlv-TJno4hbxEMT7se1Q==/109951168520849181.jpg",
          },
          {
            name: "Slow",
            picUrl: "http://p4.music.126.net/pC6aJUZMTRe_rD_6t_EbYw==/109951168548837659.jpg",
          },
          {
            name: "雨过天不晴",
            picUrl: "http://p3.music.126.net/5bqKKSxhI2w-LCicrqZPvg==/109951168483915678.jpg",
          },
          {
            name: "芯房",
            picUrl: "http://p3.music.126.net/E1RzJTmi-qCYAUQ9a1khhw==/109951168536334922.jpg",
          },
          {
            name: "床",
            picUrl: "http://p3.music.126.net/I7iZevCpkwfCj75KrNUkLw==/109951168511501593.jpg",
          },
          {
            name: "冠军情歌",
            picUrl: "http://p4.music.126.net/rYPlv-TJno4hbxEMT7se1Q==/109951168520849181.jpg",
          },
          {
            name: "迷宫",
            picUrl: "http://p3.music.126.net/KA4OfYKYT1b_3W94CIrwDg==/109951168500881027.jpg",
          },
        ],
      },

      originSong: {
        name: "原创榜",
        coverImgUrl: "https://p1.music.126.net/iFZ_nw2V86IFk90dc50kdQ==/109951166961388699.jpg",
        description: "云音乐独立原创音乐人作品官方榜单，以推荐优秀原创作品为目的。每周四网易云音乐首发。申请网易音乐人：http://music.163.com/nmusician/",
        tracks: [
          {
            name: "床",
            picUrl: "http://p4.music.126.net/I7iZevCpkwfCj75KrNUkLw==/109951168511501593.jpg",
          },
          {
            name: "经典",
            picUrl: "http://p3.music.126.net/AtAQp5otTEpV2g3ZqDwxMg==/109951168526909690.jpg",
        
          },
          {
            name: "现在 你才不幸福",
            picUrl: "http://p4.music.126.net/KTly-GTkaN8zIRBty1Mu5w==/109951168526933052.jpg",
        
          },
          {
            name: "烟花之下",
            picUrl: "http://p4.music.126.net/VWMi9irDb-PjhV-EZLwQ4A==/109951168518175925.jpg"
          },
          {
            name: "夏日痛哭企画",
            picUrl: "http://p4.music.126.net/kiwaVxpALXeg7hS7WOmu5g==/109951168521336352.jpg",
          },
          {
            name: "9.26",
            picUrl: "http://p3.music.126.net/Ws93IUrJGR_lK-QEsdKTWw==/109951168408373477.jpg",
          },
          {
            name: "戒烟报告",
            picUrl: "http://p3.music.126.net/Z3zT0QJmMdsXGwPxRHERpg==/109951168521704224.jpg",
          },
          {
            name: "8Hz",
            picUrl: "http://p4.music.126.net/8QJxoxLVT4tBF41Teb8V3w==/109951168543743744.jpg",
          },
          {
            name: "人间指南",
            picUrl: "http://p4.music.126.net/rSujVcQRdmk7eE5BwystJQ==/109951168536015065.jpg",
          },
          {
            name: "别哭了吧",
            picUrl: "http://p4.music.126.net/IDA6y2GJgUZ8L5jwRU8pgg==/109951168526860760.jpg",
          },
        ],
      },
    }
  },
}
</script>

<style scoped>
* {
  padding: 0px;
  margin: 0px;
}
.photo {
  display: flex;
  justify-content: space-between;
}
.one {
  width: 130px;
  height: 100px;
}
.name {
  text-align: center;
}
.two {
  width: 200px;
  height: 200px;
  position: relative;
  left: 50%;
  top: -130px;
}
.description {
  width: 50%;
  line-height: 30px;
}
.hr {
  height: 2px;
  width: 87%;
  background: #000;
  position: relative;
  top: -130px;
}
.show {
  height: 40px;
  font: normal 500 20px "微软雅黑";
  line-height: 40px;
  position: relative;
  top: -120px;
}
.Two {
  top: -160px;
}
.TWO {
  top: -150px;
}
</style>
