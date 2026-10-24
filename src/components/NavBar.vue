
<script setup>
import logo from "../assets/usc.png"
</script>

<template>
  <nav class="navbar">
    <router-link to="/" class="brand">
      <img :src="logo" alt="University State College Logo" class="logo" />

      <div class="school-name">
        <h2>University State College</h2>
        <p>KNOWLEDGE • INTEGRITY • EXCELLENCE</p>
      </div>
    </router-link>

    <div class="nav-links">
      <router-link to="/" exact-active-class="router-link-active">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/academics">Academics</router-link>
      <router-link to="/admissions">Admissions</router-link>
      <router-link to="/contact">Contact</router-link>
      <router-link to="/portal-login" class="portal-btn">Portal Login</router-link>
      <router-link to="/sample-data" class="portal-btn">Sample Data</router-link>
      <router-link to="/sample-methods" class="portal-btn">Sample Methods</router-link>
      <router-link to="/sample-vmodel" class="portal-btn">Sample VModel</router-link>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  min-height: 90px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 25px;
  padding: 15px 40px;
  background: #ffffff;
  border-bottom: 4px solid #f4c430;
  box-shadow: 0 3px 12px rgba(0, 51, 102, 0.08);
}

.brand {
  display: flex;
  align-items: center;
  gap: 12px;
  text-decoration: none;
  flex-shrink: 0;
}

.logo {
  width: 55px;
  height: 55px;
  object-fit: contain;
}

.school-name h2 {
  margin: 0;
  font-size: 19px;
  color: #003366;
  font-weight: 700;
}

.school-name p {
  margin: 5px 0 0;
  font-size: 10px;
  font-weight: 700;
  letter-spacing: 1px;
  color: #b88600;
}

.nav-links {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  flex-wrap: wrap;
  gap: 20px;
}

.nav-links a {
  text-decoration: none;
  color: #334b68;
  font-size: 14px;
  font-weight: 500;
  transition: color 0.2s ease;
}

.nav-links a:hover,
.nav-links a.router-link-active {
  color: #0056b3;
}

.nav-links a.router-link-active:not(.portal-btn) {
  font-weight: 700;
  text-decoration: underline;
  text-decoration-color: #f4c430;
  text-decoration-thickness: 3px;
  text-underline-offset: 7px;
}

.nav-links a.portal-btn {
  padding: 11px 17px;
  background: #0056b3;
  color: #ffffff;
  border-radius: 6px;
  font-weight: 600;
  border: 2px solid #0056b3;
}

.nav-links a.portal-btn:hover,
.nav-links a.portal-btn.router-link-active {
  background: #003366;
  border-color: #f4c430;
  color: #ffffff;
  text-decoration: none;
}

@media (max-width: 1100px) {
  .navbar {
    flex-wrap: wrap;
    padding: 18px 25px;
  }

  .nav-links {
    justify-content: flex-start;
    gap: 16px;
  }
}

@media (max-width: 600px) {
  .navbar {
    padding: 16px;
    gap: 18px;
  }

  .logo {
    width: 45px;
    height: 45px;
  }

  .school-name h2 {
    font-size: 16px;
  }

  .school-name p {
    font-size: 8px;
    letter-spacing: 0.5px;
  }

  .nav-links {
    width: 100%;
    gap: 14px;
  }

  .nav-links a {
    font-size: 13px;
  }
}
</style>
