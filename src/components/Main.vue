<template>
  <head>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.1/css/all.min.css">
  </head>
  <div class="main">
    <div class="section header">
      <div class="title"><img class="fire-icon" src="/fire_sm.png">FIRE</div>
      <div class="subtitle">
        <!-- A Dataset for<br> -->
        <!-- <span class="uns">F</span>eedback <span class="uns">I</span>ntegration and -->
        <!-- <span class="uns">R</span>efinement <span class="uns">E</span>valuation -->
        <!-- <br>of Multimodal Models -->
        A Dataset for
        <span class="uns">F</span>eedback <span class="uns">I</span>ntegration and
        <br><span class="uns">R</span>efinement <span class="uns">E</span>valuation
        of Multimodal Models
      </div>
      <div class="author-list">
        <span class="author">
          <el-link href="https://pengxiang-li.github.io">Pengxiang Li</el-link>
          <span class="ind">&#9733;1,2</span>,
        </span>
        <span class="author">
          <el-link href="https://zhigao2017.github.io/">Zhi Gao</el-link>
          <span class="ind">&#9733;2,3</span>,
        </span>
        <span class="author">
          <el-link href="https://scholar.google.com/citations?user=H8o9QtUAAAAJ&hl=en">Bofei Zhang</el-link>
          <span class="ind">&#9733;2</span>,
        </span>
        <span class="author">
          <el-link href="https://i.yt.sb/">Tao Yuan</el-link>
          <span class="ind">2</span>,
        </span>
        <span class="author">
          <el-link href="https://wu-yuwei-bit.github.io/">Yuwei Wu</el-link>
          <span class="ind">&#9993;1</span>,
        </span>
        <br>
        <span class="author">
          <el-link href="https://sites.google.com/site/mehrtashharandi">Mehrtash Harandi</el-link>
          <span class="ind">4</span>,
        </span>
        <span class="author">
          <el-link href="https://scholar.google.com/citations?user=Sl6TV7gAAAAJ&hl=en">Yunde Jia</el-link>
          <span class="ind">1</span>,
        </span>
        <span class="author">
          <el-link href="https://www.zhusongchun.net/">Song-Chun Zhu</el-link>
          <span class="ind">2,3,5</span>,
        </span>
        <span class="author">
          <el-link href="https://liqing.io/">Qing Li</el-link>
          <span class="ind">&#9993;2</span>
        </span>
      </div>
      <div class="author-list">
        <span class="org">
          <span class="ind">1</span>
          Beijing Institute of Technology
        </span>
        <span class="org">
          <span class="ind">2</span>
          Beijing Institute for Artificial General Intelligence
        </span>
        <br>
        <span class="org">
          <span class="ind">3</span>
          Peking University
        </span>
        <span class="org">
          <span class="ind">4</span>
          Monash University
        </span>
        <span class="org">
          <span class="ind">5</span>
          Tsinghua University
        </span>
      </div>

      <div class="column has-text-centered">
        <div class="publication-links">
          <!--  <span class="link-block">
                <a href="https://arxiv.org/abs/2312.10908"
                   class="external-link button is-normal is-rounded is-dark">
                  <span class="icon">
                      <i class="ai ai-arxiv"></i>
                  </span>
                  <span>arXiv</span>
                </a>
              </span> -->
          <!-- Video Link. -->
          <!-- <span class="link-block">
                <a href=""
                   class="external-link button is-normal is-rounded is-dark">
                  <span class="icon">
                      <i class="fab fa-youtube"></i>
                  </span>
                  <span>Video</span>
                </a>
              </span> -->
          <!-- Code Link. -->
          <span class="link-block">
            <a href="https://github.com/MM-FIRE/FIRE"
              class="external-link button is-normal is-rounded is-dark">
              <span class="icon">
                <i class="fab fa-github"></i>
              </span>
              <span>Code</span>
            </a>
          </span>

          <!-- Data Link. need changing -->
          <span class="link-block">
            <!-- <a target="_blank" href="" -->
            <a target="_blank" href="https://huggingface.co/datasets/PengxiangLi/FIRE/"
              class="external-link button is-normal is-rounded is-dark">
              <span class="icon">
                <i class="fa fa-database"></i>
              </span>
              <span>Data</span>
            </a>
          </span>
          <!-- <span class="link-block">
                <a href="file/clova_cvpr24_poster.pdf"
                   class="external-link button is-normal is-rounded is-dark">
                  <span class="icon">
                      <i class="fas fa-file-pdf"></i>
                  </span>
                  <span>Poster (CVPR'24)</span>
                </a>
              </span> -->

          <!-- <span class="link-block">
                <a href="file/clova_slides.pdf"
                   class="external-link button is-normal is-rounded is-dark">
                  <span class="icon">
                      <i class="fas fa-file-pdf"></i>
                  </span>
                  <span>Slides</span>
                </a>
              </span> -->
        </div>
      </div>


    </div>

    <div class="tldr">
      <p><b>TL;DR</b> We build FIRE, a dataset that empowers VLMs to integrate user feedback into the refined responses
        spontaneously, and provides a comprehensive evaluation for the feedback-refining ability of existing methods.</p>
    </div>

    <div class="section">
      <el-card class="teaser">
        <el-image src="./teaser.webp"></el-image>
      </el-card>
    </div>


    <div class="section">
      <div class="section-title">Introduction</div>
      <p class="intro">
        <b>Vision language models (VLMs)</b> have achieved impressive progress in diverse applications, becoming a prevalent
        research direction. However, VLMs can sometimes produce undesirable outputs, possibly due to omitting important details in images or misunderstanding the instructions,  which prompts the need for the <b> feedback-refining</b>  capability beyond the normal instruction-following ability. This capability enables VLMs to spontaneously refine their responses based on user feedback, enhancing the efficiency and smoothness of interactions between users and visual assistants.
        <br>
        To enhance VLM's feedback-refining capability, we build <img class="fire-icon" src="/fire_sm.png"><b>FIRE</b>, a feedback-refinement dataset, consisting of <b>1.1M</b>
        multi-turn
        conversations that are derived from <b>27 source datasets</b> , empowering VLMs to spontaneously refine their responses
        based on user feedback across diverse tasks. To scale up the data collection, FIRE is collected in two
        components: <img class="fire-icon" src="/fire_sm.png"><b>FIRE-100K</b> and <img class="fire-icon"
          src="/fire_sm.png"><b>FIRE-1M</b>, where FIRE-100K is generated by GPT-4V, and FIRE-1M is freely generated via
        models trained on FIRE-100K. Then, we build <img class="fire-icon" src="/fire_sm.png"><b>FIRE-Bench</b>, a benchmark to
        comprehensively evaluate the
        feedback-refining capability of VLMs, which contains <b>11K</b> feedback-refinement conversations as the test data, two
        evaluation settings, and a model to provide feedback for VLMs. We develop the FIRE-LLaVA model by fine-tuning
        LLaVA on FIRE-100K and FIRE-1M, which shows remarkable feedback-refining capability on FIRE-Bench and
        outperforms untrained VLMs by 50%, making more efficient user-agent interactions and underscoring the
        significance of the FIRE dataset.
      </p>
    </div>
    <div class="section">
      <div class="section-title">Statistics</div>
      <p>Notable statistics of <img class="fire-icon" src="/fire_sm.png"><b>FIRE</b></p>
      <el-carousel :interval="8000" height="450px">
        <el-carousel-item>
          <el-image class="stats-img" src="./stats/piechart.webp"></el-image>
        </el-carousel-item>
        <el-carousel-item>
          <el-image class="stats-img" src="./stats/h1.webp"></el-image>
        </el-carousel-item>
        <el-carousel-item>
          <el-image class="stats-img" src="./stats/h2.webp"></el-image>
        </el-carousel-item>
        <el-carousel-item>
          <el-image class="stats-img" src="./stats/d1.webp"></el-image>
        </el-carousel-item>
      </el-carousel>
    </div>

    <div class="section">
      <div class="section-title">Evaluation</div>
      <p class="intro">
        We design two evaluation settings: fixed dialogues and free dialogues to evaluate the performance of the student and teacher models.
        <br>
        <b>Fiexed dialogues.</b> In fixed dialogues, we evaluate whether the student and teacher models can generate appropriate responses and feedback given the conversation history, and their performance is evaluated by being compared with GPT-4V generated feedback and response, using the BLEU and CIDEr metrics to measure the textual alignment, mean absolute error (MAE) to evaluate the score given by the teacher model.
        <br>
        <b>Free dialogues.</b> We use a student model and a teacher model to perform free dialogues, and evaluate how fast and how much the student model can improve its answers based on the feedback from the teacher model. We introduce four metrics: average turn (AT), average dialogue refinement (ADR), average turn refinement (ATR), and refinement ratio (RR) for free dialogues. The AT metric evaluates how fast a VLM could achieve a satisfactory result based on feedback.  The ADR metric evaluates how much knowledge VLMs could learn from feedback in a dialogue. ATR evaluates how much knowledge VLMs could learn from feedback in one turn. RR measures the proportion of data that have a wrong initial response and a correct final response (i.e., how much data are corrected based on feedback). (Please refer to the paper for more details about the four metrics).
      
      
      </p>
      <el-carousel :interval="8000">
        <el-carousel-item>
          <el-image class="stats-img" src="./eval1.webp"></el-image>
        </el-carousel-item>
        <el-carousel-item>
          <el-image class="stats-img-1" src="./results/fixed.webp"></el-image>
        </el-carousel-item>
        <el-carousel-item>
          <el-image class="stats-img-1" src="./results/fixed-teacher.webp"></el-image>
        </el-carousel-item>
        <el-carousel-item>
          <el-image class="stats-img-1" src="./results/free.webp"></el-image>
        </el-carousel-item>

        <el-carousel-item>
          <el-image class="stats-img" src="./results/acc_turn.webp"></el-image>
        </el-carousel-item>
        <el-carousel-item>
          <el-image class="stats-img" src="./results/atr_number.webp"></el-image>
        </el-carousel-item>
        <el-carousel-item>
          <el-image class="stats-img" src="./results/adr_number.webp"></el-image>
        </el-carousel-item>
        <el-carousel-item>
          <el-image class="stats-img" src="./results/rr_number.webp"></el-image>
        </el-carousel-item>
        <el-carousel-item>
          <el-image class="stats-img" src="./results/at_number.webp"></el-image>
        </el-carousel-item>

      </el-carousel>
    </div>
    <!-- <div class="section">
      <div class="section-title">Results</div>

    </div> -->

    <div class="section">
      <div class="section-title">Examples</div>
      <p class="intro">We randomly sampled some examples from FIRE-100K, FIRE-1M, and FIRE-Bench and show them here. </p>
      <el-carousel :interval="10000" type="card" height="900px">
        <el-carousel-item v-for="d in dataset" :key="d.id" :style="{ width: '1200px' }">
          <Dialog class="example-dialog" :data="d" />
        </el-carousel-item>
      </el-carousel>
    </div>
  </div>

  <div class="footer">
    This website is inspired by <el-link href="https://mathvista.github.io/">MathVista</el-link> and <el-link
      href="https://nerfies.github.io/">Nerfies</el-link>.
  </div>
</template>

<script setup>
import Dialog from './Dialog.vue'

import { onMounted, ref } from 'vue'

const dataset = ref([])

const loadData = async () => {
  const resp = await fetch('./data/demo.json')
  // dataset.value = resp.data
  dataset.value = await resp.json()
}

onMounted(() => {
  loadData()
})
</script>

<style scoped>
.main {
  text-align: center;
  color: #333;
}

.header {
  margin: 60px 0 0 0 !important;
}

.title {
  font-size: 5em;
}

.subtitle {
  font-size: 2.5em;
  color: #555;
}

.author-list {
  margin-top: 20px;
}

.author a {
  font-size: 1.2em;
  font-weight: normal;
  color: #337ecc;
}

.org {
  margin: 0 4px 0 4px;
}

.ind {
  font-size: 0.8em;
  vertical-align: super;
}

.section {
  margin: 50px 0;
}

.tldr {
  text-align: left;
  font-size: 1em;
  max-width: 1360px;
  line-height: 150%;
}

.section-title {
  margin: 20px;
  font-size: 2em;
  font-weight: bold;
}

.uns {
  text-decoration: underline;
}

.fire-icon {
  width: 0.8em;
  height: 0.8em;
  margin-right: 0.2em;
}

.teaser {
  max-width: 1080px;
  margin: 0 auto;
}

.stats-img {
  height: 300px;
}

.stats-img-1 {
    max-width: 100%;
    max-height: 100%;
    object-fit: contain;
  }
.intro {
  text-align: justify;
  font-size: 1em;
  max-width: 1360px;
  line-height: 150%;
}

.link-block a {
  margin-top: 5px;
  margin-bottom: 5px;
}

.example-dialog {
  width: 880px;
}

.footer {
  color: #aaa;
  margin: 100px 0 60px 0;
}

/* 覆盖Element UI的默认指示器样式 */
/* 自定义轮播图指示器的样式 */
.el-carousel__indicators--outside .el-carousel__indicator.is-active button {
  background-color: #ff4d4f;
  /* 激活状态的指示器颜色 */
}

.el-carousel__indicators--outside .el-carousel__indicator button {
  background-color: #c0c4cc;
  /* 非激活状态的指示器颜色 */
  opacity: 0.7;
  /* 降低透明度以区分 */
}

.external-link {
  display: inline-block;
  padding: 8px 16px;
  /* 根据需要调整内边距 */
  margin: 4px;
  /* 根据需要调整外边距 */
  border: 1px solid #9a9c9e;
  /* 边框颜色 */
  border-radius: 9px;
  /* 边框圆角 */
  background-color: #8a8b8b;
  /* 背景颜色 */
  color: white;
  /* 文本颜色 */
  text-decoration: none;
  /* 去除下划线 */
  font-size: 20px;
  /* 字体大小 */
  transition: background-color 0.3s;
  /* 背景颜色变化的过渡效果 */
}

.external-link:hover {
  background-color: #8e8f90;
  /* 鼠标悬停时的背景颜色 */
}

.external-link .icon {
  margin-right: 8px;
  /* 图标与文本之间的间距 */
}

.external-link .fas {
  font-size: 18px;
  /* 字体大小 */
}</style>
