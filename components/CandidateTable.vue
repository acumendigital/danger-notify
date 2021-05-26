<template>
  <div>
    <tr class="table-head">
      <th class="user td-th">User ID</th>
      <th class="reg-date td-th">Registration Date</th>
      <th class="full-name td-th">Full Name</th>
      <th class="email td-th">Email Address</th>
      <th class="td-th">User Type</th>
    </tr>
    <tr v-for="el in tableElements" :key="el.userId" class="table-body">
      <td class="user td-th">{{ el.userId }}</td>
      <td class="reg-date td-th">{{ el.regDate }}</td>
      <td class="full-name td-th">{{ el.fullName }}</td>
      <td class="email td-th">{{ el.email }}</td>
      <td class="user-type td-th">
        {{ el.userType }}
      </td>
    </tr>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableElements: [
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          userType: 'Candidates',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          userType: 'Candidates',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          userType: 'Candidates',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          userType: 'Candidates',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          userType: 'Candidates',
        },
        {
          userId: 'ND1283',
          regDate: '23.04.2020',
          fullName: 'David Emodot',
          email: 'amaranth@outlook.com',
          userType: 'Candidates',
        },
      ],
    }
  },
}
</script>

<style scoped>
/* TABLE  */

table {
  margin-top: 100px;
  width: 100%;
  background-color: white;
  border-radius: 8px;
}

.table-top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 40px;
}

.table-top-text {
  font-size: 16px;
  font-weight: 300;
}

.table-head {
  background-color: #f5f8ff;
  padding: 0 40px;
}

tr {
  display: flex;
  padding: 0 40px;
}

th {
  font-weight: 600;
}

.td-th {
  padding: 25px 0;
  width: 20%;
  display: flex;
}

.user {
  width: 15%;
}

.email {
  width: 28%;
}

.user-type {
  color: rgba(0, 166, 157, 1);
}
</style>
