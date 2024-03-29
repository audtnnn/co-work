<template>
  <section id="selection">
      <div class="main_logo">
            {{logo_type}}
      </div>
      <div class="block">
      </div>
      <ul class="gallery">
        <li v-for="(item, index) in gallery_data" :key="index" @mouseover="handleHover(index)" @mouseleave="handleLeave(index)">
          <router-link :to="item.link" class="detail">
            <div :class="item.headline">
              <h2 class="__title" :class="{ 'on': onport == index }">{{item.type}}</h2>
            </div>
            <div class="app" :class="{ 'on': onport == index }">
              <img :src="item.image" alt="" class="app_img" :class="{ 'on': onport == index }">
              <div class="app_detail">{{item.app_detail}}</div>
            </div>
            <div class="detail_phrase" :class="{ 'on': onport == index}">
              {{item.phrase}}
            </div>
          </router-link>
        </li>
    </ul>
  </section>
</template>

<script>
export default {
data(){
  return {
    logo: false,
    basisc: "여행할땐",
    gallery_data: [
      {
        link: "main", headline: "headline", logo: "검색할땐" ,type: "여기", phrase: "최저가 숙소 찾는다면", image: "src/assets/image/mascot.jpg"
      },
      {
        link: "survey", headline: "headline2", logo: "추천여행" , type: "어때", phrase: "여행, 어디로 가야할까?", image: "src/assets/image/mascot1.png"
      }
    ],
    logo_type: "여행할땐",
    onport : null
  }
},
    methods: {
      handleHover(index) {
        const hoveredItem = this.gallery_data[index];
        this.logo_type = hoveredItem.logo
        this.onport = index;
      },
      handleLeave() {
        this.logo_type = "여행할땐"
        this.onport = null;
      }
  }
};
</script>

<style>
.selection {
line-height: 1.5em;
margin: 0;
position: relative;
}
a {
text-decoration: none;
display: block;
}
.gallery {
list-style: none;
margin: 0;
padding: 0;
display: flex;
height: 90vh;
overflow: hidden;
}
.gallery li {
flex: 1;
transition: 0.8s;
position: relative;
}
.block {
position: absolute;
top: 20%;
left: 50%;
transform: translate(-50%, -50%);
z-index: 99999;
width: 150px;
height: 1300px;
}
.main_logo {
position: absolute;
top: 35%;
left: 50%;
transform: translate(-50%, -50%);
z-index: 99999;
font-family: "YeogiEottae", sans-serif;
color: rgb(209, 42, 42);
font-size: 60px;
font-weight: 300;
 transition: all 0.5s;

}
.app {
  position: absolute;
  top: 37.5%;
  left: 62.5%;
  opacity: 0;
  transition: all 0.5s;
  transform: translateY(10%);
}
.gallery li:nth-child(2) .app {
  transform: translateX(-470px);
}
.app.on {
  opacity: 1;
}
.app_img {
  border-radius: 15px;
  width: 100px;
  height: 100px;
  border-radius: 15px;
  transition: all 0.5s
}
.app_img.on {
  box-shadow: 1px 1px 8px rgba(225, 225, 225, 0.8);
}
.gallery li:nth-child(2).app_img {
  box-shadow: -1px 1px 8px rgba(225, 225, 225, 0.8);
}
.app_detail {
  font-size: 23px;
  font-family: "Pretendard";
  color: #fff;
  font-weight: 600;
}
.detail_phrase {
  color: rgb(209, 42, 42);
  font-size: 50px;
  opacity: 0;
  position: absolute;
  top: 40%;
  left: 20%;
  font-family: "YeogiEottae", sans-serif;
  transition: opacity 0.5s, color 0.2s 0.7s;
}
.detail_phrase.on {
  opacity: 1;
  color: #fff;
}
.gallery li:nth-child(2) .detail_phrase {
  transform: translateX(40%);
}
.headline {
position: absolute;
top: 40%;
left: 80%;
}
.headline2 {
position: absolute;
top: 40%;
right: 80%;
}

.__title {
font-family: "YeogiEottae", sans-serif;
font-size: 60px;
font-weight: 300;
text-align: center;
color: #fff;
display: inline-block;
width: 118px;
height: 72px;
animation: fadeIn 1s;
 transition: color 0.2s 0.8s;
}
.__title.on {
  color: rgb(209, 42, 42);
}
@keyframes fadeIn {
                from {
                    opacity: 0;
                }
                to {
                    opacity: 1;
                }
            }
.detail {
display: block;
}
/* .detail {
font-family: "Noto Sans KR", sans-serif;
 width:150px;
 height:50px;
 border-radius:25px;
 background:rgba(0,0,0,0.5);
 color:#fff;
 font-weight: bold;
 font-size:15px; 
 text-align:center;
 line-height:50px; 
} */
/* .detail:hover {
background:#fff;
color: #000;
} */
.gallery li:last-child {
border-right: none;
}
.gallery li:nth-child(1) {
background: url(/src/assets/image/test1.jpg)no-repeat left;
background-size: 1905px;
}
.gallery li:nth-child(2) {
background: url(/src/assets/image/test1.jpg)no-repeat right;
background-size: 1905px;
}
.gallery:hover li {
flex: 1;
filter: grayscale(1);
}
.gallery li:hover {
flex: 1.9;
filter: grayscale(0);
z-index: 999;
}
</style>