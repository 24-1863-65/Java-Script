
<template>
  <main class="home">
    <section class="hero">
      <div class="hero-content">
        <div class="established">
          <span></span>
          YOUR FUTURE STARTS HERE
        </div>

        <h1>
          Learn Today.
          <em>Lead</em>
          <br />
          Tomorrow.
        </h1>

        <div class="yellow-line"></div>

        <p class="description">
          Welcome to University State College, where knowledge meets
          opportunity. We are committed to providing quality education,
          developing practical skills, and preparing students to become
          responsible and future-ready professionals.
        </p>

        <div class="buttons">
          <router-link to="/academics" class="primary">
            Explore Academics
          </router-link>

          <router-link to="/admissions" class="secondary">
            Apply for Admission
          </router-link>
        </div>

        <div class="stats">
          <div class="stat-item">
            <h2>20+</h2>
            <p>Academic Programs</p>
          </div>

          <div class="stat-item">
            <h2>5,000+</h2>
            <p>Students</p>
          </div>

          <div class="stat-item">
            <h2>50+</h2>
            <p>Qualified Faculty</p>
          </div>

          <div class="stat-item">
            <h2>100%</h2>
            <p>Driven by Excellence</p>
          </div>
        </div>

        <p class="stats-note">
          Sample statistics for demonstration purposes.
        </p>
      </div>

      <div class="hero-image">
        <div class="image-card">
          <div class="logo-circle">
            <img
              src="../assets/usc.png"
              alt="University State College Logo"
            />
          </div>

          <p class="card-label">WELCOME TO</p>

          <h2>
            University<br />
            State College
          </h2>

          <div class="small-line"></div>

          <h4>KNOWLEDGE • INTEGRITY • EXCELLENCE</h4>

          <p class="motto">
            "Empowering Minds,<br />
            Building Futures."
          </p>
        </div>
      </div>
    </section>

    <section class="values">
      <div class="values-heading">
        <p class="section-label">WHY CHOOSE US</p>

        <h2>Education That Moves You Forward</h2>

        <p>
          Discover an environment where you can learn, grow, and prepare
          for the opportunities ahead.
        </p>
      </div>

      <div class="values-grid">
        <article class="value-card">
          <div class="value-icon">01</div>
          <h3>Quality Education</h3>
          <p>
            Build a strong foundation through learning experiences
            that develop knowledge and practical skills.
          </p>
        </article>

        <article class="value-card">
          <div class="value-icon">02</div>
          <h3>Student Development</h3>
          <p>
            Discover your strengths, develop your talents, and grow
            through academic and personal experiences.
          </p>
        </article>

        <article class="value-card">
          <div class="value-icon">03</div>
          <h3>Future-Ready Skills</h3>
          <p>
            Prepare for changing industries with critical thinking,
            creativity, collaboration, and problem-solving skills.
          </p>
        </article>
      </div>
    </section>
  </main>
</template>

<style scoped>
* {
  box-sizing: border-box;
}

.home {
  min-height: calc(100vh - 90px);
  background: #f5f8ff;
  color: #1e293b;
  font-family: Arial, Helvetica, sans-serif;
}

/* Hero Section */
.hero {
  display: flex;
  align-items: center;
  gap: 45px;
  padding: 60px;
  background: #ffffff;
}

.hero-content {
  width: 55%;
}

.established {
  color: #b88600;
  font-size: 13px;
  font-weight: 700;
  letter-spacing: 2px;
  display: flex;
  align-items: center;
  gap: 12px;
}

.established span {
  width: 40px;
  height: 3px;
  background: #f4c430;
}

.hero-content h1 {
  color: #003366;
  font-family: Georgia, serif;
  font-size: 54px;
  line-height: 1.12;
  margin: 28px 0 24px;
}

.hero-content h1 em {
  color: #e5ad00;
  font-weight: normal;
}

.yellow-line {
  width: 65px;
  height: 4px;
  background: #f4c430;
  margin-bottom: 24px;
  border-radius: 4px;
}

.description {
  color: #52647a;
  font-size: 16px;
  line-height: 1.9;
  max-width: 600px;
}

/* Buttons */
.buttons {
  display: flex;
  flex-wrap: wrap;
  gap: 14px;
  margin-top: 28px;
}

.primary,
.secondary {
  display: inline-block;
  padding: 15px 23px;
  font-size: 14px;
  font-weight: 700;
  text-decoration: none;
  text-align: center;
  border-radius: 6px;
  cursor: pointer;
  transition: 0.2s ease;
}

.primary {
  background: #0056b3;
  color: #ffffff;
  border: 2px solid #0056b3;
}

.primary:hover {
  background: #003366;
  border-color: #003366;
}

.secondary {
  background: #ffffff;
  color: #0056b3;
  border: 2px solid #f4c430;
}

.secondary:hover {
  background: #fff7d6;
}

/* Statistics */
.stats {
  margin-top: 35px;
  padding: 20px 10px;
  display: grid;
  grid-template-columns: repeat(4, minmax(0, 1fr));
  background: #f5f8ff;
  border: 1px solid #e0e9f7;
  border-radius: 10px;
  gap: 8px;
}

.stat-item {
  text-align: center;
  padding: 5px 8px;
  border-right: 1px solid #d5e1ef;
}

.stat-item:last-child {
  border-right: none;
}

.stat-item h2 {
  color: #0056b3;
  margin: 0;
  font-size: 23px;
}

.stat-item p {
  margin: 8px 0 0;
  font-size: 11px;
  line-height: 1.5;
  color: #52647a;
}

.stats-note {
  font-size: 11px;
  color: #8493a5;
  margin-top: 8px;
}

/* University Card */
.hero-image {
  width: 45%;
  display: flex;
  justify-content: center;
}

.image-card {
  width: 100%;
  max-width: 440px;
  min-height: 490px;
  padding: 35px 25px;
  border: 1px solid #f4d56b;
  border-radius: 20px;
  background: linear-gradient(
    145deg,
    #fff1ad,
    #ffffff 50%,
    #dceaff
  );
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  box-shadow: 0 12px 35px rgba(0, 51, 102, 0.12);
  text-align: center;
}

.logo-circle {
  width: 155px;
  height: 155px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #ffffff;
  border: 2px solid #f4d56b;
  border-radius: 50%;
  margin-bottom: 25px;
  padding: 12px;
}

.logo-circle img {
  width: 100%;
  height: 100%;
  object-fit: contain;
}

.card-label {
  color: #b88600;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 3px;
  margin: 0 0 12px;
}

.image-card h2 {
  color: #003366;
  font-family: Georgia, serif;
  font-size: 31px;
  line-height: 1.25;
  margin: 0;
}

.small-line {
  width: 65px;
  height: 3px;
  background: #f4c430;
  margin: 22px 0;
  border-radius: 4px;
}

.image-card h4 {
  color: #0056b3;
  font-size: 10px;
  letter-spacing: 2px;
  line-height: 1.8;
  margin: 0;
}

.motto {
  color: #52647a;
  font-family: Georgia, serif;
  font-style: italic;
  font-size: 17px;
  line-height: 1.7;
  margin-top: 22px;
}

/* Values Section */
.values {
  padding: 65px 60px 75px;
  background: #f5f8ff;
}

.values-heading {
  text-align: center;
  max-width: 650px;
  margin: 0 auto 35px;
}

.section-label {
  color: #b88600;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 2px;
}

.values-heading h2 {
  color: #003366;
  font-family: Georgia, serif;
  font-size: 32px;
  line-height: 1.3;
  margin: 12px 0;
}

.values-heading > p:last-child {
  color: #64748b;
  line-height: 1.8;
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 22px;
  max-width: 1200px;
  margin: 0 auto;
}

.value-card {
  background: #ffffff;
  padding: 28px;
  border: 1px solid #e0e9f7;
  border-radius: 12px;
  box-shadow: 0 5px 18px rgba(0, 51, 102, 0.04);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.value-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 10px 25px rgba(0, 51, 102, 0.09);
}

.value-icon {
  width: 45px;
  height: 45px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  background: #fff1ad;
  color: #003366;
  font-size: 14px;
  font-weight: 700;
}

.value-card h3 {
  color: #003366;
  font-size: 18px;
  margin: 20px 0 12px;
}

.value-card p {
  color: #64748b;
  font-size: 14px;
  line-height: 1.8;
  margin-bottom: 0;
}

/* Responsive */
@media (max-width: 1100px) {
  .hero {
    padding: 50px 35px;
    gap: 30px;
  }

  .hero-content h1 {
    font-size: 44px;
  }

  .stats {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .stat-item:nth-child(2) {
    border-right: none;
  }

  .stat-item:nth-child(1),
  .stat-item:nth-child(2) {
    border-bottom: 1px solid #d5e1ef;
    padding-bottom: 14px;
  }

  .stat-item:nth-child(3),
  .stat-item:nth-child(4) {
    padding-top: 14px;
  }
}

@media (max-width: 760px) {
  .hero {
    flex-direction: column;
    align-items: stretch;
    padding: 45px 22px;
  }

  .hero-content,
  .hero-image {
    width: 100%;
  }

  .hero-content h1 {
    font-size: 39px;
  }

  .hero-image {
    margin-top: 20px;
  }

  .image-card {
    min-height: 430px;
  }

  .values {
    padding: 50px 22px;
  }

  .values-grid {
    grid-template-columns: 1fr;
  }

  .values-heading h2 {
    font-size: 27px;
  }
}

@media (max-width: 420px) {
  .hero-content h1 {
    font-size: 33px;
  }

  .buttons {
    flex-direction: column;
  }

  .primary,
  .secondary {
    width: 100%;
  }

  .image-card h2 {
    font-size: 27px;
  }

  .stats {
    padding: 15px 5px;
  }

  .stat-item h2 {
    font-size: 20px;
  }
}
</style>
