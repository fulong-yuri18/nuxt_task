<template>
  <div class="student_id">
		<div>
			<h2>{{ getStudentname }}</h2>
			<div class="link">
				<NuxtLink to="/students">生徒一覧へ戻る</NuxtLink>|
				<NuxtLink to="/management">トップページへ</NuxtLink>
			</div>
		</div>
  </div>
</template>


<script>
export default {
	validate({ params }) {
		if (params.id === undefined) {
      return false
    } else {
      return true
    }
	},
	props: ['studentid'],
  data() {
    return {
      students: [
        {
          id: "qnfungqxllc3m1ak",
          name: "生徒A",
        },
        {
          id: "7j9cumkgsq6l264c",
          name: "生徒B",
        },
        {
          id: "eo34bhey9m0d92ou",
          name: "生徒C",
        },
      ],
    };
  },
  computed: {
    getStudentname: function () {
      return this.students.filter(x => x.id === this.$route.params.id)[0].name;
    }
  }
};
</script>


<style>
.student_id {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.link{
	display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
