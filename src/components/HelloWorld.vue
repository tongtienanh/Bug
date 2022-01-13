<template>
  <div>
     <table>
        <thead class="ant-table-thead">
         <tr class="table-header">
          <th class="ant-table-cell-fix-left" style="background: #F2F2F2">
            <v-btn class="" v-if="!checkRoute" width="24" height="24" icon @click="onChangeCheckboxAll">
              <v-icon
                  :class="{ 'color-checkbox': changeIcon}"
                  class="">{{ changeIcon ? 'mdi-checkbox-marked' : 'mdi-checkbox-blank-outline' }}
              </v-icon>
            </v-btn>
          </th>
        </tr>
        </thead>
      <template v-for="contact in tableComfirm">
        <tr class="table-content" :key="contact">
          <td
            class="ant-table-cell-fix-left"
            style="left: 0"
          >
            <v-btn width="24" height="24" class="mr-0" icon @click="contact.isCheck = !contact.isCheck">
              <v-icon
                :color="contact.isCheck ? '#e91e63' : ''"
                :class="{ '': changeIcon }"
                style="font-size:20px"
              >
                {{
                  contact.isCheck
                    ? "mdi-checkbox-marked"
                    : "mdi-checkbox-blank-outline"
                }}
              </v-icon>
            </v-btn>
          </td>
        </tr>
      </template>
    </table>
  </div>
</template>
<script>
export default {
  components: {
  },
  data() {
    return {
      tableComfirm:[
        {"id":268,"contactId":24603,"customerId":34469,"code":"VH024603","isManual":0,"hasOrder":1,"mobile":"0985247162","email":"","userName":"nhung","parentName":"nhung","createdAt":"2022-01-11 09:56:04","updatedAt":"2022-01-11 09:56:04","deletedAt":null,"contactTutorPractice":[{"id":624,"contactTutorId":268,"contactId":24603,"subjectId":1,"monCode":"toan","gradeId":null,"vhResultId":null,"status":6,"statusLink":null,"testLink":null,"interviewStatus":null,"interviewUser":null,"interviewComment":null,"appointmentTime":null,"appointmentAt":null,"appointmentTestLevel":1,"appointmentLink":null,"testResult":null,"testResultCreatedAt":null,"commentStatus":null,"commentBy":null,"commentContent":null,"commentLearningPath":null,"operatorId":null,"operatorName":null,"interviewCalenderId":null,"learningPathLink":null,"videoLink":null,"type":1,"isHotOrder":1,"createdBy":1,"updatedBy":100004,"createdAt":"2022-01-11 09:56:04","updatedAt":"2022-01-12 17:38:21","deletedAt":null,"statusLabel":"Đã book lịch PV","interviewName":"","learningPathLinkCopy":null,"videoLinkCopy":null,"comfirmed":false,"canceled":false,"menu":false},{"id":625,"contactTutorId":268,"contactId":24603,"subjectId":3,"monCode":"ta","gradeId":null,"vhResultId":null,"status":6,"statusLink":null,"testLink":null,"interviewStatus":null,"interviewUser":null,"interviewComment":null,"appointmentTime":null,"appointmentAt":null,"appointmentTestLevel":1,"appointmentLink":null,"testResult":null,"testResultCreatedAt":null,"commentStatus":null,"commentBy":null,"commentContent":null,"commentLearningPath":null,"operatorId":null,"operatorName":null,"interviewCalenderId":null,"learningPathLink":null,"videoLink":null,"type":2,"isHotOrder":1,"createdBy":1,"updatedBy":100004,"createdAt":"2022-01-11 09:56:04","updatedAt":"2022-01-12 17:38:21","deletedAt":null,"statusLabel":"Đã book lịch PV","interviewName":"","learningPathLinkCopy":null,"videoLinkCopy":null,"comfirmed":false,"canceled":false,"menu":false},{"id":626,"contactTutorId":268,"contactId":24603,"subjectId":3,"monCode":"ta","gradeId":null,"vhResultId":null,"status":6,"statusLink":null,"testLink":null,"interviewStatus":null,"interviewUser":null,"interviewComment":null,"appointmentTime":"2022-01-14 00:00:00","appointmentAt":20220114,"appointmentTestLevel":1,"appointmentLink":null,"testResult":null,"testResultCreatedAt":null,"commentStatus":null,"commentBy":null,"commentContent":null,"commentLearningPath":null,"operatorId":null,"operatorName":null,"interviewCalenderId":394,"learningPathLink":null,"videoLink":null,"type":2,"isHotOrder":0,"createdBy":1,"updatedBy":1,"createdAt":"2022-01-12 17:40:47","updatedAt":"2022-01-12 17:40:47","deletedAt":null,"statusLabel":"Đã book lịch PV","interviewName":"","learningPathLinkCopy":null,"videoLinkCopy":null,"comfirmed":false,"canceled":false,"menu":false},{"id":628,"contactTutorId":268,"contactId":24603,"subjectId":3,"monCode":"ta","gradeId":null,"vhResultId":null,"status":6,"statusLink":null,"testLink":null,"interviewStatus":null,"interviewUser":null,"interviewComment":null,"appointmentTime":"2022-01-13 09:30:00","appointmentAt":20220113,"appointmentTestLevel":1,"appointmentLink":null,"testResult":null,"testResultCreatedAt":null,"commentStatus":null,"commentBy":null,"commentContent":null,"commentLearningPath":null,"operatorId":null,"operatorName":null,"interviewCalenderId":396,"learningPathLink":null,"videoLink":null,"type":2,"isHotOrder":0,"createdBy":1,"updatedBy":1,"createdAt":"2022-01-13 08:43:50","updatedAt":"2022-01-13 08:43:50","deletedAt":null,"statusLabel":"Đã book lịch PV","interviewName":"","learningPathLinkCopy":null,"videoLinkCopy":null,"comfirmed":false,"canceled":false,"menu":false},{"id":630,"contactTutorId":268,"contactId":24603,"subjectId":3,"monCode":"ta","gradeId":null,"vhResultId":null,"status":6,"statusLink":null,"testLink":null,"interviewStatus":null,"interviewUser":null,"interviewComment":null,"appointmentTime":"2022-01-13 09:00:00","appointmentAt":20220113,"appointmentTestLevel":1,"appointmentLink":null,"testResult":null,"testResultCreatedAt":null,"commentStatus":null,"commentBy":null,"commentContent":null,"commentLearningPath":null,"operatorId":null,"operatorName":null,"interviewCalenderId":397,"learningPathLink":null,"videoLink":null,"type":2,"isHotOrder":0,"createdBy":1,"updatedBy":1,"createdAt":"2022-01-13 08:44:53","updatedAt":"2022-01-13 08:44:53","deletedAt":null,"statusLabel":"Đã book lịch PV","interviewName":"","learningPathLinkCopy":null,"videoLinkCopy":null,"comfirmed":false,"canceled":false,"menu":false}],"birthday":2015,"customers":[{"id":34469,"contactId":24603,"fullName":"nhung","birthday":2015,"position":"child"}],"isCheck":false},
        {"id":267,"contactId":21136,"customerId":27023,"code":"VH021136","isManual":1,"hasOrder":0,"mobile":"0345547777","email":"","userName":"diễm test 3","parentName":"diễm","createdAt":"2022-01-10 16:51:05","updatedAt":"2022-01-10 16:51:05","deletedAt":null,"contactTutorPractice":[{"id":623,"contactTutorId":267,"contactId":21136,"subjectId":1,"monCode":"toan","gradeId":4,"vhResultId":null,"status":6,"statusLink":null,"testLink":"https://dev.vuihoc.vn/tutoring/intro?student_name=di%E1%BB%85m%20test%203&parent_name=di%E1%BB%85m&last_example_point=&birthday=2016&phone=0345547777&subject_alias=toan&level=&grade_id=4&core_user_id=4808&tutorPracticeId=623","interviewStatus":null,"interviewUser":null,"interviewComment":null,"appointmentTime":"2022-01-11 16:50:00","appointmentAt":20220111,"appointmentTestLevel":null,"appointmentLink":null,"testResult":null,"testResultCreatedAt":null,"commentStatus":null,"commentBy":null,"commentContent":null,"commentLearningPath":null,"operatorId":null,"operatorName":null,"interviewCalenderId":null,"learningPathLink":null,"videoLink":null,"type":1,"isHotOrder":0,"createdBy":596,"updatedBy":596,"createdAt":"2022-01-10 16:51:05","updatedAt":"2022-01-12 17:38:21","deletedAt":null,"statusLabel":"Đã book lịch PV","interviewName":"","learningPathLinkCopy":null,"videoLinkCopy":null,"comfirmed":false,"canceled":false,"menu":false},{"id":627,"contactTutorId":267,"contactId":21136,"subjectId":3,"monCode":"ta","gradeId":null,"vhResultId":null,"status":6,"statusLink":null,"testLink":null,"interviewStatus":null,"interviewUser":null,"interviewComment":null,"appointmentTime":"2022-01-14 00:00:00","appointmentAt":20220114,"appointmentTestLevel":1,"appointmentLink":null,"testResult":null,"testResultCreatedAt":null,"commentStatus":null,"commentBy":null,"commentContent":null,"commentLearningPath":null,"operatorId":null,"operatorName":null,"interviewCalenderId":394,"learningPathLink":null,"videoLink":null,"type":2,"isHotOrder":0,"createdBy":1,"updatedBy":1,"createdAt":"2022-01-12 17:41:29","updatedAt":"2022-01-12 17:41:29","deletedAt":null,"statusLabel":"Đã book lịch PV","interviewName":"","learningPathLinkCopy":null,"videoLinkCopy":null,"comfirmed":false,"canceled":false,"menu":false},{"id":629,"contactTutorId":267,"contactId":21136,"subjectId":3,"monCode":"ta","gradeId":null,"vhResultId":null,"status":6,"statusLink":null,"testLink":null,"interviewStatus":null,"interviewUser":null,"interviewComment":null,"appointmentTime":"2022-01-13 09:30:00","appointmentAt":20220113,"appointmentTestLevel":1,"appointmentLink":null,"testResult":null,"testResultCreatedAt":null,"commentStatus":null,"commentBy":null,"commentContent":null,"commentLearningPath":null,"operatorId":null,"operatorName":null,"interviewCalenderId":396,"learningPathLink":null,"videoLink":null,"type":2,"isHotOrder":0,"createdBy":1,"updatedBy":1,"createdAt":"2022-01-13 08:44:01","updatedAt":"2022-01-13 08:44:01","deletedAt":null,"statusLabel":"Đã book lịch PV","interviewName":"","learningPathLinkCopy":null,"videoLinkCopy":null,"comfirmed":false,"canceled":false,"menu":false},{"id":631,"contactTutorId":267,"contactId":21136,"subjectId":3,"monCode":"ta","gradeId":null,"vhResultId":null,"status":6,"statusLink":null,"testLink":null,"interviewStatus":null,"interviewUser":null,"interviewComment":null,"appointmentTime":"2022-01-13 09:00:00","appointmentAt":20220113,"appointmentTestLevel":1,"appointmentLink":null,"testResult":null,"testResultCreatedAt":null,"commentStatus":null,"commentBy":null,"commentContent":null,"commentLearningPath":null,"operatorId":null,"operatorName":null,"interviewCalenderId":397,"learningPathLink":null,"videoLink":null,"type":2,"isHotOrder":0,"createdBy":1,"updatedBy":1,"createdAt":"2022-01-13 08:45:06","updatedAt":"2022-01-13 08:45:06","deletedAt":null,"statusLabel":"Đã book lịch PV","interviewName":"","learningPathLinkCopy":null,"videoLinkCopy":null,"comfirmed":false,"canceled":false,"menu":false}],"birthday":2016,"customers":[{"id":27023,"contactId":21136,"fullName":"diễm test 3","birthday":2016,"position":"child"}],"isCheck":false},
        {"id":266,"contactId":22250,"customerId":29326,"code":"VH022250","isManual":1,"hasOrder":1,"mobile":"0912345607","email":"","userName":"diễm con 1","parentName":"diễm test 1","createdAt":"2022-01-10 16:24:41","updatedAt":"2022-01-10 16:24:41","deletedAt":null,"contactTutorPractice":[{"id":622,"contactTutorId":266,"contactId":22250,"subjectId":1,"monCode":"toan","gradeId":5,"vhResultId":null,"status":6,"statusLink":null,"testLink":"https://dev.vuihoc.vn/tutoring/intro?student_name=di%E1%BB%85m%20con%201&parent_name=di%E1%BB%85m%20test%201&last_example_point=&birthday=2015&phone=0912345607&subject_alias=toan&level=&grade_id=5&core_user_id=19537&tutorPracticeId=622","interviewStatus":null,"interviewUser":null,"interviewComment":null,"appointmentTime":"2022-01-11 16:24:00","appointmentAt":20220111,"appointmentTestLevel":null,"appointmentLink":null,"testResult":null,"testResultCreatedAt":null,"commentStatus":null,"commentBy":null,"commentContent":null,"commentLearningPath":null,"operatorId":null,"operatorName":null,"interviewCalenderId":null,"learningPathLink":null,"videoLink":null,"type":1,"isHotOrder":0,"createdBy":595,"updatedBy":595,"createdAt":"2022-01-10 16:24:41","updatedAt":"2022-01-12 17:38:21","deletedAt":null,"statusLabel":"Đã book lịch PV","interviewName":"","learningPathLinkCopy":null,"videoLinkCopy":null,"comfirmed":false,"canceled":false,"menu":false}],"birthday":2015,"customers":[{"id":29326,"contactId":22250,"fullName":"diễm con 1","birthday":2015,"position":"child"},{"id":29327,"contactId":22250,"fullName":"diễm con 2","birthday":2017,"position":"child"}],"isCheck":false}
      ]
    };
  },
   created() {
   
  },
  methods: {
    onChangeCheckboxAll() {
      this.changeIcon = !this.changeIcon
      this.tableComfirm.forEach(contact => contact.isCheck = !contact.isCheck)
    },
  },

};
</script>