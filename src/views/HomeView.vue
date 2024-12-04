<script setup lang="ts">
import {ref} from "vue";
const url =
  'https://fuss10.elemecdn.com/a/3f/3302e58f9a181d2509f3dc0fa68b0jpeg.jpeg'
const srcList = [
  'https://fuss10.elemecdn.com/a/3f/3302e58f9a181d2509f3dc0fa68b0jpeg.jpeg',
  'https://fuss10.elemecdn.com/1/34/19aa98b1fcb2781c4fba33d850549jpeg.jpeg',
  'https://fuss10.elemecdn.com/0/6f/e35ff375812e6b0020b6b4e8f9583jpeg.jpeg',
  'https://fuss10.elemecdn.com/9/bb/e27858e973f5d7d3904835f46abbdjpeg.jpeg',
  'https://fuss10.elemecdn.com/d/e6/c4d93a3805b3ce3f323f7974e6f78jpeg.jpeg',
  'https://fuss10.elemecdn.com/3/28/bbf893f792f03a54408b3b7a7ebf0jpeg.jpeg',
  'https://fuss10.elemecdn.com/2/11/6535bcfb26e4c79b48ddde44f4b6fjpeg.jpeg',
]
const radio=ref('pic');
const ShowMoreStory=ref(false);
</script>

<template>
  <div class="leaf">
    <div class="left" />
    <div class="move" />
    <div class="right" />
  </div>

  <el-main class="main">
    <div class="person-info">
      <div class="avatar-box">
        <div class="avatar-border">
          <div class="avatar" />
        </div>
      </div>
      <div class="info-text">
        <p class="name">王国强</p>
        <p class="detail">
          <span>汉族</span>
        </p>
        <p class="detail">
          <span>浙江省</span>
        </p>
        <p class="detail">
          <span>杭州市</span>
        </p>
        <p class="detail">
          <span>拱墅区</span>
        </p>
        <p class="time">
          <span>1950.06.11-2023.05.07</span>
        </p>
      </div>
    </div>

    <div class="video">
      <p class="title">影响生平志</p>
      <video class="player" src="@/assets/video.mp4" controls></video>
    </div>

    <div class="story">
      <p class="title">生平故事</p>
      <div class="right">
        <p class="content">1950年6月11日出生在浙江省杭州市一个幸福的小家庭父母都是铁路职工。1968年8月高中毕业在当地的锅炉厂参加工作。1970年1月因工作努力受到厂里嘉奖成为工组组长。1973年2被评为优秀职工厂劳动模范。1977年1月与李某某结为伉俪二人育有一子。1978年调为销售科任副科长。1980年任销售科科长。1985年被评为杭州市劳动模范年底任厂党委副书记。1990年辞职下海成立杭州零零壹贸易有公司。1995年杭州零零壹贸易有限公司荣获浙江省知名企业。2000年合并成立零零贰贸易有限公司任集团董事长。2003年被评为浙江省知名企业家。2005年在其领导下的企业进行数字化转型升级，引领科技创新荣获省、市国家级创新奖项20多项。2010年功成身退，任浙江省知名企业家协会名誉主席。2022年11月12日在亲人朋友的陪伴 于杭州家里溘然长逝。</p>
        <p class="read-more">
          <el-link type="primary" @click="ShowMoreStory = true">展开显示</el-link>
        </p>
        <el-dialog
          v-model="ShowMoreStory"
          title="生平故事"
          width="90%"
        >
          <p class="content">1950年6月11日出生在浙江省杭州市一个幸福的小家庭父母都是铁路职工。1968年8月高中毕业在当地的锅炉厂参加工作。1970年1月因工作努力受到厂里嘉奖成为工组组长。1973年2被评为优秀职工厂劳动模范。1977年1月与李某某结为伉俪二人育有一子。1978年调为销售科任副科长。1980年任销售科科长。1985年被评为杭州市劳动模范年底任厂党委副书记。1990年辞职下海成立杭州零零壹贸易有公司。1995年杭州零零壹贸易有限公司荣获浙江省知名企业。2000年合并成立零零贰贸易有限公司任集团董事长。2003年被评为浙江省知名企业家。2005年在其领导下的企业进行数字化转型升级，引领科技创新荣获省、市国家级创新奖项20多项。2010年功成身退，任浙江省知名企业家协会名誉主席。2022年11月12日在亲人朋友的陪伴 于杭州家里溘然长逝。</p>
          <template #footer>
            <div class="dialog-footer">
              <el-button @click="ShowMoreStory = false">关闭</el-button>
            </div>
          </template>
        </el-dialog>
      </div>
    </div>

    <div class="images">
      <p class="title">影像留念</p>
<!--      <video class="player" src="@/assets/video.mp4" controls></video>-->
      <div class="radio">
        <el-radio-group v-model="radio" text-color="#000000" fill="#000000">
          <el-radio value="pic" size="large" class="btn1"><span>图片</span></el-radio>
          <el-radio value="vid" size="large" class="btn2"><span>视频</span></el-radio>
        </el-radio-group>
      </div>
      <div class="pictures" v-if="radio=='pic'">
        <el-image
          :src="url"
          :zoom-rate="1.2"
          :max-scale="7"
          :min-scale="0.2"
          :preview-src-list="srcList"
          :initial-index="4"
          fit="cover"
          class="images"
        />
        <p class="read-more">
          <el-link type="primary" @click="void(0)">显示更多</el-link>
        </p>
      </div>
      <div class="videos" v-if="radio=='vid'">
        <video class="player" src="https://img.shuzimubei.com/uploads/20240507/6bddebcccc49343a4a9f37a1b52c70ee" controls></video>
        <p class="read-more">
          <el-link type="primary" @click="void(0)">显示更多</el-link>
        </p>
      </div>
    </div>
    <div class="whisper" />
    <div class="friend-said">
      <div class="title">
        <img src="@/assets/friend_left.png" alt="friend left" />
        <span>亲友寄语</span>
        <img src="@/assets/friend_right.png" alt="friend right" />
      </div>
      <div class="list">
        <div class="item">
          <p class="content">我的父亲是一个很聪明、很会做生意、又很有责任心的一个人，他一直是我人生中的标杆，是我前进的动力。</p>
          <p class="name">—儿子 </p>
          <p class="date">2024-05-27</p>
        </div>
        <div class="item">
          <p class="content">他是一个非常努力的人，对工作极其上心，同时，他也很关心家人，是一个模范的丈夫和负责人的父亲。</p>
          <p class="name">—妻子</p>
          <p class="date">2024-05-27</p>
        </div>
        <div class="item">
          <p class="content">他是一位拥有坚韧不拔意志品质的任，他的人生充满了奋斗和成就，他的才华和勇气令人敬佩。</p>
          <p class="name">—同事</p>
          <p class="date">2024-05-27</p>
        </div>
        <div class="item">
          <p class="content">他极具创造力，总能在普通的日常生活中找出新的创意和解决问题的办法。他的思维敏捷，察人所未察，无论在工作还是在生活中，都让人觉得非常有新意。</p>
          <p class="name">—合作伙伴</p>
          <p class="date">2024-05-27</p>
        </div>
        <div class="item">
          <p class="content">他遇事冷静果断，能够迅速作出决策，是一个优秀的领导者。</p>
          <p class="name">—好友</p>
          <p class="date">2024-05-27</p>
        </div>
        <div class="item">
          <p class="content">所有的事情都有尽头，唯独思念没有，我们非常想他</p>
          <p class="name">—表弟</p>
          <p class="date">2024-05-27</p>
        </div>
        <div class="item">
          <p class="content">他是一位乐观、积极向上的人，他的微笑常常能够照亮最黑暗的角落，他的坚韧和勇气鼓舞人心。</p>
          <p class="name">—侄女</p>
          <p class="date">2024-05-27</p>
        </div>
        <div class="item">
          <p class="content">他不仅是位备受尊敬的企业家，也是一位出色的公益事业倡导者。</p>
          <p class="name">—好友</p>
          <p class="date">2024-05-27</p>
        </div>
      </div>
      <p class="show-more">
        <el-link type="primary" @click="void(0)">显示更多</el-link>
      </p>
    </div>
    <div class="leaveMessages">
      <p class="title">留下你对他的思念</p>
    </div>
    <div class="write-message">
      <el-form>
        <el-form-item label="姓名">
          <el-input placeholder="请输入您的姓名" />
        </el-form-item>
        <el-form-item label="留言">
          <el-input placeholder="请输入你的留言" />
        </el-form-item>
        <div class="confirm">
          <span>文字留言</span>
        </div>
      </el-form>
    </div>
  </el-main>
</template>

<style scoped lang="scss">
.leaf {
  width: 100vw;
  position: absolute;
  >* {
    width: 100%;
    height: 222px;
    position: absolute;
    background-repeat: round;
  }
  .left {
    background-image: url("@/assets/leftleaf.png");;
  }
  .right {
    background-image: url("@/assets/rightleaf.png");
  }
  .move {
    background-image: url("@/assets/moveleaf.png");
  }
}
.main {
  height: 2390px;
  background: url("@/assets/background.jpg");
  background-size: 100% auto;
  .person-info {
    margin-top: 100px;
    height: 200px;
    .avatar-box {
      width: 181px;
      height: 200px;
      float: left;
      .avatar-border {
        background-image: url("@/assets/avatar_border.png");
        background-repeat: no-repeat;
        background-size: 100% 100%;
        height: 96%;
        width: 126%;
      }
      .avatar {
        background-image: url("@/assets/avatar.png");
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center center;
        width: 124px;
        height: 180px;
        position: relative;
        left: 45px;
        top: 5px;
      }
    }
    .info-text {
      float: left;
      margin-left: 20px;
      p.name {
        font-size: 25px;
        margin-top: 10px;
        margin-bottom: 16px;
      }
      p.detail {
        font-size: 16px;
        margin: 4px 0;
        span {
          border-bottom: 1px solid #9db3ae;
        }
      }
      p.time {
        font-size: 16px;
        margin: 4px 0;
        span {
          border-bottom: 2px solid #9db3ae;
        }
      }
    }
  }
  .video{
    margin-top: 40px;
    width: 100%;
    .title{
      clear: left;
      letter-spacing: 12px;
      text-align: center;
      font-size: 17px;
      line-height: 41px;
      font-weight: 700;
      background-image: url("@/assets/video_title_border.png");
      background-position: center center;
      background-repeat: no-repeat;
      background-size: auto 100%;
    }
    .player{
      margin-top:20px;
      width:100%;
      height: 180px;
      background-color: #000;
    }
  }
  .story {
    margin-top: 100px;
    height:275px;
    .title {
      writing-mode: vertical-lr;
      letter-spacing: 13px;
      font-size: 17px;
      font-weight: bold;
      color: #1b2933;
      background-image: url("@/assets/story_title_border.png");
      background-repeat: no-repeat;
      background-size: auto 100%;
      width: 40px;
      height: 165px;
      text-align: center;
      padding-left: 34px;
      float: left;
    }
    .right {
      float: left;
      width: calc(100% - 100px);
      margin-left: 16px;
      .content {
        text-indent: 2em;
        font-size: 12px;
      }
      .read-more {
        text-align: right;
      }
    }
  }

  .images{
    margin-top: 30px;
    width: 100%;
    .title{
      clear: left;
      letter-spacing: 10px;
      text-align: center;
      font-size: 18px;
      line-height: 40px;
      font-weight: 700;
      background-image: url("@/assets/recording.png");
      background-position: center center;
      background-repeat: no-repeat;
      background-size: auto 100%;
    }
    ::v-deep .el-radio__input{
      display: none !important;
    }
    .radio{
      margin-top: 30px;
      color: gray;
      .btn1{
        color: gray;
      }
      .is-checked{
        span{
          color: black !important;
          border-bottom: 1px solid #000000;
        }
      }
      .btn1:hover{
        color: gray;
      }
    }
    .pictures{
      //margin-top: 20px;
      .images{
        width:150px;
        height:150px;
      }
      .read-more {
        margin-top: 15px;
        text-align: right;
      }
    }

    .videos{
      margin-top:20px;
      .player{
        width:150px;
        height: 150px;
        background-color: #000;
      }
      .read-more {
        margin-top: 15px;
        text-align: right;
      }
    }
  }
  .whisper {
    background-image: url("@/assets/envelope.webp");
    width: 328px;
    height: 168px;
    background-repeat: no-repeat;
    background-size: cover;
    margin-left: auto;
    margin-right: auto;
  }
  .friend-said {
    .title {
      text-align: center;
      margin-top: 20px;
      span {
        margin: 0 7px;
        text-align: center;
        font-size: 17px;
        font-weight: 600;
        letter-spacing: 7px;
      }
    }
    .list {
      margin-top: 16px;
      .item {
        p {
          font-size: 12px;
          line-height: 1.3;
        }
        .name {
          text-align: right;
        }
        .date {
          text-align: right;
        }
      }
    }
    .show-more {
      text-align: right;
      margin-top: 10px;
      font-size: 13px;
      letter-spacing: 4px;
    }
  }
  .leaveMessages{
    margin-top: 30px;
    width: 100%;
    .title{
      clear: left;
      width: 250px;
      height: 51px;
      letter-spacing: 7px;
      text-align: center;
      font-size: 18px;
      line-height: 40px;
      font-weight: 700;
      background-image: url("@/assets/leaveMsg.png");
      background-position: center center;
      background-repeat: no-repeat;
      background-size: 100% 100%;
      margin: 0 auto;
    }
  }
  .write-message {
    width: 91%;
    height: 150px;
    background-image: url("@/assets/name_and_msg_background.png");
    background-repeat: no-repeat;
    background-size: 100% 100%;
    padding: 25px 30px 0;
    .confirm {
      text-align: right;
      padding-right: 20px;
      span {
        color: #423f3f;
        border-radius: 4px;
        background-image: url("@/assets/msg_confirm.png");
        background-repeat: no-repeat;
        background-size: 100% 100%;
        width: 80px;
        height: 22px;
        letter-spacing: 1px;
        font-size: 13px;
      }
    }
  }
}


</style>
