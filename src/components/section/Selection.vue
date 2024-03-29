<template>
    <section id="selection">
        <ul class="gallery">
          <div class="main_logo">
              여행할땐
          </div>
          <li>
            <router-link to="main" class="detail">
              <div class="headline">
                <h2 class="__title">여기</h2>
              </div>
            </router-link>
          </li>
          <li>
            <router-link to="survey" class="detail">
              <div class="headline2">
                <h2 class="__title">어때</h2>
              </div>
            </router-link>
          </li>
      </ul>
    </section>
</template>

<script>
export default {
 
};
</script>

<style>
.selection {
  line-height: 1.5em;
  margin: 0;
}
a {
  text-decoration: none;
}
.gallery {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  height: 90vh;
}
.gallery li {
  flex: 1;
  transition: 0.5s;
  position: relative;
}
.main_logo {
  position: absolute;
  top: 30%;
  left: 50%;
  transform: 
  
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
  color: rgb(209, 42, 42);
  font-size: 60px;
  font-weight: 300;
  text-align: center;
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
flex: 3;
filter: grayscale(0);
z-index: 9999;
}
.headline .headline2 {
  position: absolute;
  background: #000;
  color: #fff;
  text-align: center;
}
</style>
