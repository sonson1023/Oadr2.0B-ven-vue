<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />-->
    <nav class="navbar navbar-inverse">
      <div class="container-fluid">
        <div class="navbar-header">
          <button
            type="button"
            class="navbar-toggle"
            data-toggle="collapse"
            data-target="#myNavbar"
          >
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </button>
          <a class="navbar-brand" href="#">Logo</a>
        </div>
        <div class="collapse navbar-collapse" id="myNavbar">
          <ul class="nav navbar-nav">
            <li class="active">
              <router-link to="/">Intro</router-link>
            </li>
            <li>
              <router-link to="/eiregister">EiRegister</router-link>
            </li>
            <li>
              <router-link to="/eiopt">EiOpt</router-link>
            </li>
          </ul>
          <ul class="nav navbar-nav navbar-right">
            <li>
              <!-- <router-link to="/Login" class="glyphicon glyphicon-log-in">Login</router-link> -->
              <div class="g-signin2" data-onsuccess="onSignIn"></div>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <router-view/>
    <footer class="container-fluid text-center">
      <p>Footer Text</p>
    </footer>
  </div>
</template>

<style>
/* #app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
} */

/* Remove the navbar's default margin-bottom and rounded borders */
.navbar {
  margin-bottom: 0;
  border-radius: 0;
}

/* Set height of the grid so .sidenav can be 100% (adjust as needed) */
.row.content {
  height: 450px;
}

/* Set gray background color and 100% height */
.sidenav {
  padding-top: 20px;
  background-color: #f1f1f1;
  height: 100%;
}

/* Set black background color, white text and some padding */
footer {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 5%;
  background: #ccc;
}

/* On small screens, set height to 'auto' for sidenav and grid */
@media screen and (max-width: 767px) {
  .sidenav {
    height: auto;
    padding: 15px;
  }
  .row.content {
    height: auto;
  }
}
</style>

<script>
var GoogleAuth; // Google Auth object.
function initClient() {
  gapi.client
    .init({
      apiKey: "HgQIRsiuuHPON-LlUSi_KVlH",
      clientId:
        "759816036599-49ea9beeqvkieu39nvmst4d6a0hrroce.apps.googleusercontent.com",
      scope: "https://www.googleapis.com/auth/drive.metadata.readonly",
      discoveryDocs: [
        "https://www.googleapis.com/discovery/v1/apis/drive/v3/rest"
      ]
    })
    .then(function() {
      GoogleAuth = gapi.auth2.getAuthInstance();

      // Listen for sign-in state changes.
      GoogleAuth.isSignedIn.listen(updateSigninStatus);
    });
}

function onSignIn(googleUser) {
  var profile = googleUser.getBasicProfile();
  console.log("ID: " + profile.getId()); // Do not send to your backend! Use an ID token instead.
  console.log("Name: " + profile.getName());
  console.log("Image URL: " + profile.getImageUrl());
  console.log("Email: " + profile.getEmail()); // This is null if the 'email' scope is not present.
}
export default {
  data: function() {
    return {
      title: "My Title"
    };
  },
  // Usage with context the component
  head: {
    // To use "this" in the component, it is necessary to return the object through a function
    title: function() {
      return {
        inner: this.title
      };
    },
    meta: [
      {
        name: "google-signin-client_id",
        content:
          "759816036599-49ea9beeqvkieu39nvmst4d6a0hrroce.apps.googleusercontent.com"
      }
    ],
    link: [
      {
        rel: "stylesheet",
        href:
          "https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/css/bootstrap.min.css"
      }
    ],
    script: [
      {
        src:
          "https://maxcdn.bootstrapcdn.com/bootstrap/3.4.0/js/bootstrap.min.js"
      },
      { src: "https://apis.google.com/js/platform.js" }
    ]
  }
};
</script>

