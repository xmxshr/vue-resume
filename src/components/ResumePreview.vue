<template>
  <div id="preview">
    <section class="profile">
      <h1>{{resume.profile.name}}</h1>
      <p>
        <span>{{resume.profile.birth}}</span>
        <span> | {{resume.profile.city}}</span>
        <span> | {{resume.profile.for}}</span>
      </p>
    </section>
    <section class="resumeField fieldTitle">
      <h2><span>工作经历</span></h2>
      <div class="item-ct" v-for="(item, index) in resume.workExperience" :key="index">
        <p class="time">{{item.time}}</p>
        <div class="part">
          <h4>{{item.company}}</h4>
          <p>{{item.content}}</p>
        </div>
      </div>
    </section>
    <section class="resumeField fieldTitle">
      <h2><span>教育背景</span></h2>
      <div class="item-ct" v-for="(item, index) in resume.education" :key="index">
          <p class="time">{{item.time}}</p>
          <p class="time">{{item.school}}</p>
          <p class="time">{{item.degree}}</p>
        
      </div>
    </section>
    <section class="resumeField fieldTitle">
      <h2><span>项目经历</span></h2>
      <div class="item-ct" v-for="(item, index) in resume.project" :key="index">
        <div class="part">
          <h4>{{item.name}}</h4>
          <p>{{item.content}}</p>
        </div>
      </div>
    </section>
    <section class="resumeField fieldTitle">
      <h2><span>获奖情况</span></h2>
      <div class="item-ct" v-for="(item, index) in resume.awards" :key="index">
        <div class="part">
          <h4>{{item.name}}</h4>
          <p>{{item.content}}</p>
        </div>
      </div>
    </section>
    <section class="contact fieldTitle">
      <h2><span>联系方式</span></h2>
      <p>QQ：{{resume.contact.qq}}</p>
      <p>微信：{{resume.contact.wechat}}</p>
      <p>电话：{{resume.contact.phone}}</p>
      <p>邮箱：{{resume.contact.email}}</p>
    </section>
  </div>
</template>

<script>
import {mapState} from 'vuex'

export default {
  computed: {
    ...mapState([
      'resume'
    ])
  }
}
</script>


<style lang="scss">
#preview {
  padding: 40px;
  overflow: auto;
  color: #333;
  .profile{
    >h1{
      padding-bottom: 16px;
      font-size: 36px;
    }
  }
  .resumeField{
    .item-ct{
      margin-left: 8px;
      display: flex;
      flex-direction: row;
      justify-content: flex-start;
      margin-bottom: 24px;
      
      .time{
        font-size: 18px;
        line-height: 24px;
        min-width: 135px;
        font-weight: 600;
        margin-right: 48px;
      }
      .part{
        flex: 1;
        >h4{
          font-size: 18px;
          margin-bottom: 16px;
        }
      }
    }
  }
  .fieldTitle{
    margin-top: 40px;
    >h2{
      font-size: 22px;
      padding-bottom: 16px;
      margin-bottom: 16px;
      border-bottom: 1px solid #ccc;
      >span{
        background: #ccc;
      }
    }
  }
  .contact{
    >p{
      margin: 0 0 8px 8px;
    }
  }
}
</style>
