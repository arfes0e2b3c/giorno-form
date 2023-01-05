<template>
  <div id="app">
  <h2>ジョルノ新歓</h2>
    <form
      action="https://docs.google.com/forms/u/0/d/e/1FAIpQLSewr_1oG2xSe91CJ5CKVmUYBnDMAGSa9j1IdnL-GtUmuStKCw/formResponse"
      class="contact"
      method="post"
    >
      <div class="contact__list m-5">
        <div class="contact__item mb-3">
          <label for="name" class="form-label">名前<span>（フルネーム・漢字）</span></label>
          <input
            type="text"
            name="entry.79336790"
            id="name"
            placeholder="回答を入力"
            required
            class="form-control" 
          />
        </div>
        <div class="contact__item mb-3">
          <label for="company" class="form-label">名前の読みがな<span>（ひらがな）</span></label>
          <input
            type="text"
            name="entry.104180904"
            id="mail"
            placeholder="回答を入力"
            required
            class="form-control" 
          />
        </div>
        <div class="contact__item mb-3">
          <label for="contents" class="form-label"
            >LINEの登録名（本名と同一でもご記入をお願いします）</label
          >
          <input
            type="text"
            name="entry.1512870593"
            id="contents"
            placeholder="回答を入力"
            required
            class="form-control" 
          />
        </div>
        <div class="contact__item mb-3">
          <label for="contents" class="form-label">性別</label>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.617564716"
            value="男性"
            />
            <label class="form-check-label" for="entry.617564716">男性</label>
          </div>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.617564716"
            value="女性"
            />
            <label class="form-check-label" for="entry.617564716">女性</label>
          </div>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.617564716"
            value="その他"
            />
            <label class="form-check-label" for="entry.617564716">その他</label>
          </div>
        </div>
        <div class="contact__item mb-3">
          <label for="contents" class="form-label">学年(４月からの新学年)</label>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.782386193"
            value="新１年生"
            />
            <label class="form-check-label" for="entry.782386193">新１年生</label>
          </div>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.782386193"
            value="新２年生"
            />
            <label class="form-check-label" for="entry.782386193">新２年生</label>
          </div>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.782386193"
            value="その他"
            />
            <label class="form-check-label" for="entry.782386193">その他</label>
          </div>
        </div>
        <div class="contact__item mb-3">
          <label for="faculty" class="form-label">学部</label>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.235945975"
            value="経済学部"
            v-model="other"
            />
            <label class="form-check-label" for="entry.235945975">経済学部</label>
          </div>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.235945975"
            value="経営学部"
            v-model="other"
            />
            <label class="form-check-label" for="entry.235945975">経営学部</label>
          </div>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.235945975"
            value="都市科学部"
            v-model="other"
            />
            <label class="form-check-label" for="entry.235945975">都市科学部</label>
          </div>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.235945975"
            value="教育学部"
            v-model="other"
            />
            <label class="form-check-label" for="entry.235945975">教育学部</label>
          </div>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.235945975"
            value="理工学部"
            v-model="other"
            />
            <label class="form-check-label" for="entry.235945975">理工学部</label>
          </div>
        </div>
        <div class="contact__item mb-3" v-show="otherTrue">
          <label for="faculty" class="form-label">学部</label>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.235945975"
            value="数理"
            v-model="other"
            />
            <label class="form-check-label" for="entry.235945975">数理</label>
          </div>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.235945975"
            value="数理"
            v-model="other"
            />
            <label class="form-check-label" for="entry.235945975">数理</label>
          </div>
          <div class="form-check">
            <input
            class="form-check-input"
            type="radio"
            name="entry.235945975"
            value="数理"
            v-model="other"
            />
            <label class="form-check-label" for="entry.235945975">数理</label>
          </div>
          
        </div>
        <button type="submit" class="btn btn-primary">送信</button>
      </div>
    </form>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
    </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return{
      other: '理工学部'
    }
  },
  computed: {
    otherTrue() {
      return this.other === '理工学部'
    }
  }
}
</script>
