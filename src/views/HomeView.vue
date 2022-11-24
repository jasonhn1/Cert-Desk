<script lang="ts">
import { defineComponent } from 'vue';
import { ElMessageBox } from 'element-plus';
export default defineComponent({
  name: 'App',
  data() {
    return {
      scrollPosition: null as unknown as number,
      dialogVisible: false,
    }
  },
  methods: {
    studentClick() {
      window.location.replace("https://m.certitude-demo.delta.games");
    },
    handleClose(done: () => void) {
      ElMessageBox.confirm('Are you sure to close this dialog?')
        .then(() => {
          done()
        })
        .catch(() => {
          // catch error
        })
    },
  },
});
</script>

<template>
  <header class="headSplash p-relative" id="home">
    <!-- <div class="particles">
      <img src="@/assets/particles_blurred.png" alt="spinning particles" class="animation-image" />
    </div> -->
    <div class="container">
      <el-row>
        <el-col>
          <div class="wrapper p-relative overall-content">
            
            <div class="content text-cert">
              <h1 class="context">Certitude is Seamless</h1>
              <div class="rectangle"></div>
              <p>
                Our revolutionary education verification
                platform is simple, instant, and secure
              </p>
              <div class="buttons">
                <!-- <el-button class="bgradient" type="warning" @click="dialogVisible = true" round>I am a recruiter</el-button>
                
                <el-button class="bgradient" @click="studentClick" round>I am a Student</el-button> -->
                
                <button class="student-btn">Student <el-icon><CircleCheckFilled /></el-icon></button>
                <br/>
                <button class="recruiter">Recruiter<el-icon id="manage"><Briefcase /></el-icon></button>
                <br/>

                <!-- <button class="student">I am a Student <el-icon><Notebook /></el-icon></button> -->
              </div>
            </div>
            

              <el-card class="box-card center card-box">
                <div class="card-horizontal">
                <div class="text item">
                  <el-icon :size="30" color="#ff7315" class="no-inherit">
                    <Pointer />
                  </el-icon>
                  <h2>One-Click Check</h2>
                  <p>
                    Students send credentials instantly through a secure link
                  </p>
                </div>
                <div class="vertical-bar"></div>
                <div class="text item">
                  <el-icon :size="30" color="#ff7315" class="no-inherit">
                    <SetUp />
                  </el-icon>
                  <h2>Data Belongs to Students</h2>
                  <p>
                    Business won't share data on signup and only see what you send
                  </p>
                </div>
              </div>
              </el-card>
          </div>
        </el-col>
      </el-row>
    </div>
  </header>

  <el-row id="about">
    <div class="container">
      <el-row>
        <el-col :span="12" style="padding-left:50px">
          <div class="wrapper p-relative">
            <div class="secondary-content">
              <h1>About Us</h1>
              <p>
                We are a team of students and professionals who are passionate about education and technology. We
                believe that education is the key to a better future and that technology can help us achieve that
                future. We are building a platform that will help students and businesses connect and verify each
                other's credentials in a seamless and secure way.
              </p>
            </div>
          </div>
        </el-col>
      </el-row>
    </div>
  </el-row>
  <el-row id="contact">
    <div class="container">
      <el-row>
        <el-col :span="24">
          <div class="wrapper p-relative">
            <div class="secondary-content">
              <h2>Contact Us!</h2>
              <el-form size="large" label-width="120px" class="demo-dynamic">
                <el-form-item prop="email" label="Email">
                  <el-input />
                </el-form-item>
                <el-form-item label="Message" prop="desc">
                  <el-input type="textarea" rows="15" />
                </el-form-item>
                <el-form-item>
                  <el-button type="primary">Submit</el-button>
                </el-form-item>
              </el-form>
            </div>
          </div>
        </el-col>
      </el-row>
    </div>
  </el-row>
  <el-footer class="footer" height="300">
    I guess copyright or something can go here<br />
    should also make this<br />
    taller<br />
    with links<br />
    and stuff
  </el-footer>
  <el-dialog v-model="dialogVisible" title="Employer Auth" width="30%" :before-close="handleClose">
    <span>Authentication options for the employer should be shown here</span>
    <template #footer>
      <span class="dialog-footer">
        <el-button @click="dialogVisible = false">Cancel</el-button>
        <el-button type="primary" @click="dialogVisible = false">
          Confirm
        </el-button>
      </span>
    </template>
  </el-dialog>
</template>

<style scoped>
.footer {
  background: darkslategray;
  padding: 1em;
  color: white;
  text-align: center;
}

.container {
  max-width: 1350px;
  width: 100%;
  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto;
}

.headSplash {
  background-image: url('@/assets/certitude_bg.png');
  background-size: cover;
  background-repeat: no-repeat;
  /* background-image: url('@/assets/splashbanner.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: 50%;
  overflow: hidden; */
}

#manage{
  margin-bottom: 20px;
  margin-left:-10px;
  width: 50px;
  height: 55px;
}
.recruiter{
  border: 3px;
  width: 160px;
  height: 60px;
  font-family:'Archivo Black';
  font-size: 20px;
  color: black;
  border-radius: 5px;
  margin-top: 20px;
  padding-left:15px;
  padding-right:0;
  background: linear-gradient(90deg, rgba(251,146,51,1) 0%, rgba(252,181,49,1) 40%, rgba(254,209,50,1) 100%);
  box-shadow: 12px 12px 2px 1px rgb(0, 0, 0);
}

.student-btn{
  border: 3px;
  width: 160px;
  height: 60px;
  font-family:'Archivo Black';
  font-size: 20px;
  color: black;
  border-radius: 5px;
  margin-top: 20px;
  background: linear-gradient(90deg, rgba(251,146,51,1) 0%, rgba(252,181,49,1) 40%, rgba(254,209,50,1) 100%);
  box-shadow: 12px 12px 2px 1px rgb(0, 0, 0);
}
.card-horizontal{
  display: flex;
  flex-direction: row;
}
.particles {
  position: absolute;
  left: 10%;
}

.animation-image {
  width: 30vw;
  animation: spin 20s linear infinite;
}

.rectangle{
  position: absolute;
  width: 260px;
  height: 35px;
  margin-top: -40px;
  margin-left: 296px;
  z-index: 0;
  background: linear-gradient(90deg, rgba(251,146,51,1) 0%, rgba(252,181,49,1) 40%, rgba(254,209,50,1) 100%);
  border-radius: 8px;
}



@keyframes spin {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}

.content {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  margin-right: 200px;
}

.vertical-bar{
  border-left: 3px solid rgb(61, 61, 61);
  margin-top: 100px;
  margin-left: 20px;
  margin-right: 20px;
  height: 100px;
}

.overall-content {
  height: 100%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
  margin-top: 200px;
}

.secondary-content {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.card-box{
  height: 260px;
  width: 1000px;
  margin-top: 300px;
  margin-bottom: 200px;
}
.text-cert{
  margin-top: -400px;
  margin-left: 100px;
}
</style>