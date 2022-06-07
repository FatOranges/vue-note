<template>
  <div v-for="item in cards" :key="item.id" class="card">
    <div class="imgBx">
      <img :src="item.src" alt="">
    </div>

    <div class="content">
      <div class="details">
        <h2>{{item.chinaName}}
          <br> <span>{{item.englishName}}</span>
        </h2>
        <div class="data">
          <h3>{{ item.Posts }} <br><span>Posts</span></h3>
          <h3>{{ item.Followers }} <br><span>Followers</span></h3>
          <h3>{{ item.Following }} <br><span>Following</span></h3>
        </div>
        <div class="actionBtn">
          <button>Follow</button>
          <button>message</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
 data: function () {
   return {
     cards: [
       {
         id: '1',
         chinaName: '中国移动',
         englishName: 'China Mobile Communications Group Co',
         Posts: 342,
         Followers: '120K',
         Following: 285,
         src: './src/assets/wallhaven-q2k8yr.jpg'
       },
       {
         id: '2',
         chinaName: '中国移动',
         englishName: 'China Mobile Communications Group Co',
         Posts: 342,
         Followers: '120K',
         Following: 285,
         src: './src/assets/wallhaven-o3mxj9.png'
       },
       {
         id: '3',
         chinaName: '中国移动',
         englishName: 'China Mobile Communications Group Co',
         Posts: 342,
         Followers: '120K',
         Following: 285,
         src: './src/assets/wallhaven-l3x1ky.jpg'
       }
     ]
   }
 }
}
</script>

<style>
  .card {
    position: relative;
    float: left;
    margin: 0 40px;
    width: 350px;
    height: 190px;
    border-radius: 20px;
    background: #fff;
    box-shadow: 0 35px 80px rgba(0, 0, 0, 0.15);
    transition: 0.5s;
  }

  .card:hover {
    height: 450px;
  }

  .card .imgBx {
    position: absolute;
    left: 50%;
    top: -50px;
    transform: translateX(-50%);
    width: 150px;
    height: 150px;
    border-radius: 20px;
    box-shadow: 0 15px 50px rgba(0, 0, 0, 0.35);
    overflow: hidden;
    transition: 0.5s;
  }

  .card:hover .imgBx {
    width: 250px;
    height: 250px;
  }

  .card .imgBx img {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  .card .content {
    position: absolute;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: flex-end;
    overflow: hidden;
  }

  .card .content .details {
    padding: 40px;
    text-align: center;
    width: 100%;
    transition: 0.5s;
    transform: translateY(150px);
  }

  .card:hover .content .details {
    transform: translateY(0px);
  }

  .card .content .details h2 {
    font-size: 1.2em;
    font-weight: 600;
    line-height: 1.2em;
    color: #555;
  }

  .card .content .details h2 span {
    font-size: 0.75em;
    font-weight: 500;
    opacity: 0.5;
  }

  .card .content .details .data {
    display: flex;
    justify-content: space-between;
    margin: 20px 0;
  }

  .card .content .details .data h3 {
    font-size: 1em;
    color: #555;
    line-height: 1.2em;
    font-weight: 600;
  }

  .card .content .details .data h3 span {
    font-size: 0.85em;
    opacity: 0.5;
    font-weight: 400;
  }

  .card .content .details .actionBtn {
    display: flex;
    justify-content: space-between;
  }

  .card .content .details .actionBtn button {
    padding: 10px 30px;
    border-radius: 5px;
    border: none;
    outline: none;
    font-size: 1em;
    font-weight: 500;
    background: #ff5f95;
    color: #fff;
    cursor: pointer;
  }

  .card .content .details .actionBtn button:nth-child(2) {
    border: 1px solid #999;
    color: #999;
    background: #fff;
  }
</style>
