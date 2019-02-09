<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <h3>Request Mesage Info</h3>
        <table class="table table-striped">
          <thead>
            <tr>
              <th>VEN ID</th>
              <th>VEN Name</th>
              <th>VEN Type</th>
              <th>VTN IP</th>
              <th>VTN Port</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>
                <input type="text" id="venID" v-model="venID" placeholder="asdsq84-ivjbu1203ugnd">
                <label for="venID"></label>
              </td>
              <td>
                <input type="text" id="venName" v-model="venName" placeholder="ven1">
                <label for="venName"></label>
              </td>
              <td>
                <input type="text" id="vtnIP" v-model="vtnIP" placeholder="127.0.0.0">
                <label for="vtnIP"></label>
              </td>
              <td>
                <input type="text" id="vtnPort" v-model="vtnPort" placeholder="8080">
                <label for="vtnPort"></label>
              </td>
              <td>
                <div>
                  <label for="ven2.0B" class="radio-inline">
                    <input type="radio" id="ven2.0B" value="B" v-model="venType">2.0B
                  </label>
                  <label for="ven2.0A" class="radio-inline">
                    <input type="radio" id="ven2.0A" value="A" v-model="venType">2.0A
                  </label>
                </div>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
    <div class="row">
      <div class="col-xs-6">
        <h3>Request Message</h3>
      </div>
      <div class="col-xs-6">
        <h3>Response Message</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      venType: false,
      venID: null,
      vtnIP: null,
      vtnName: null,
      vtnPort: 8080
    };
  },
  mounted() {}
};
</script>
