<template>
  <div class="userdetail">
    <div>
      <div class="user_img">
        <img :src="userInfo.user_img" v-if="userInfo.user_img">
        <img src="../../assets/default_img.jpg" v-else>
      </div>
      <div class="user_edit">
        <div>
          <p>
            <span>0</span>
            <span class="user_text">粉丝</span>
          </p>
          <p>
            <span>0</span>
            <span class="user_text">关注</span>
          </p>
          <p>
            <span>0</span>
            <span class="user_text">获赞</span>
          </p>
        </div>
        <div @click="$router.push('/edit')">
          <div class="user_editBtn">编辑资料</div>
        </div>
      </div>
    </div>
    <div>
      <h2>{{userInfo.name}}</h2>
      <p v-if="userInfo.user_desc">{{userInfo.user_desc}}</p>
      <p v-else>这个人很嬾，什么都没有写</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'userdetail',
  props: ['userInfo']
}
</script>

<style lang='scss' scoped>
.userdetail {
  background-color: white;
  padding: 0 3.333vw;
  >div:nth-child(1) {
    display: flex;
    padding: 5.556vw 0;
      .user_img {
        margin-right: 5.556vw;
        img {
          height: 23.611vw;
          width: 23.611vw;
          border-radius: 50%;
        }
      }
    .user_edit {
      flex: 1;
      div:nth-child(1) {
      display: flex;
        p {
          flex: 1;
          display: flex;
          justify-content: center;
          align-items: center;
          flex-direction: column;
          font-size: 3.889vw;
          .user_text {
            color: #aaa;
          }
        }
        p:nth-child(1), p:nth-child(2) {
          border-right: 0.278vw solid #ccc;
        }
      }
    div:nth-child(2) {
      padding: 1.389vw 2.778vw;
        .user_editBtn {
          border: 0.278vw solid #fb7a9f;
          padding: 0.833vw;
          display: flex;
          align-items: center;
          justify-content: center;
          color: #fb7a9f;
          border-radius: 1.111vw;
        }
      }
    }
  }
  >div:nth-child(2) {
    h2{
      margin: 10.001px 0 2.999px 0;
      font-weight: 400;
    }
    p {
      padding: 0;
      margin: 2.778vw 0;
      color: #999;
    }
  }
}
</style>
