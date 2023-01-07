<template>
  <div id="app">
    <form
      action="https://docs.google.com/forms/u/0/d/e/1FAIpQLSewr_1oG2xSe91CJ5CKVmUYBnDMAGSa9j1IdnL-GtUmuStKCw/formResponse"
      class="contact"
      method="post"
    >
      <h2>ジョルノ新歓</h2>
      <div class="contact__list m-5">
        <div class="contact__item mb-3" v-for="name in names" :key="name.id">
          <label :for="name" class="form-label">{{ name.title }}</label>
          <input
            type="text"
            :name="name.formName"
            id="name"
            placeholder="回答を入力"
            required
            class="form-control"
          />
        </div>
        <div class="contact__item mb-3">
          <label for="contents" class="form-label">性別</label>
          <div class="form-check" v-for="gender in genders" :key="gender.id">
            <input
              class="form-check-input"
              type="radio"
              name="entry.617564716"
              value="gender.value"
            />
            <label class="form-check-label" for="entry.617564716">{{
              gender.value
            }}</label>
          </div>
        </div>
        <div class="contact__item mb-3">
          <label for="contents" class="form-label"
            >学年(４月からの新学年)</label
          >
          <div class="form-check" v-for="grade in grades" :key="grade.id">
            <input
              class="form-check-input"
              type="radio"
              name="entry.782386193"
              :value="grade.value"
            />
            <label class="form-check-label" for="entry.782386193">{{
              grade.value
            }}</label>
          </div>
        </div>
        <div class="contact__item mb-3">
          <label for="faculty" class="form-label">学部</label>
          <div
            class="form-check"
            v-for="faculty in faculties"
            :key="faculty.id"
          >
            <input
              class="form-check-input"
              type="radio"
              name="entry.235945975"
              :value="faculty.value"
              v-model="selectedFaculty"
            />
            <label class="form-check-label" for="entry.235945975">{{
              faculty.value
            }}</label>
          </div>
        </div>
        <div class="contact__item mb-3" v-show="isFacultyST">
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
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
      crossorigin="anonymous"
    />
  </div>
</template>
<script>
export default {
  data() {
    return {
      selectedFaculty: "",
      names: [
        {
          id: 1,
          name: "chn-alpha",
          title: "名前(フルネーム・漢字)",
          formName: "entry.79336790",
        },
        {
          id: 2,
          name: "hiragana",
          title: "名前の読みがな（ひらがな）",
          formName: "entry.104180904",
        },
        {
          id: 3,
          name: "line-name",
          title: "LINEの登録名（本名と同一でもご記入をお願いします）",
          formName: "entry.1512870593",
        },
      ],
      genders: [
        { id: 1, value: "男性" },
        { id: 2, value: "女性" },
        { id: 3, value: "その他" },
      ],
      grades: [
        { id: 1, value: "新１年生" },
        { id: 2, value: "新２年生" },
        { id: 3, value: "その他" },
      ],
      faculties: [
        { id: 1, value: "経済学部" },
        { id: 2, value: "経営学部" },
        { id: 3, value: "都市科学部" },
        { id: 4, value: "教育学部" },
        { id: 5, value: "理工学部" },
      ],
    };
  },
  computed: {
    isFacultyST() {
      return this.selectedFaculty === "理工学部";
    },
  },
};
</script>
