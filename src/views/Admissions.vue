
<template>
  <div class="page">
    <header class="hero">
      <div class="container">
        <p class="eyebrow">University State College</p>
        <h1>Start Your Journey With Us</h1>
        <p class="lead">
          Take the next step toward your future. Explore our academic
          programs and discover the opportunities waiting for you
          at University State College.
        </p>
        <button class="primary-btn" @click="scrollToFees">
          Explore Admission
        </button>
      </div>
    </header>

    <main class="container main">
      <section class="card">
        <h2>Admission Requirements</h2>

        <div class="requirements-grid">
          <div>
            <h3>Admission Process</h3>
            <ul>
              <li>Complete the application form.</li>
              <li>Submit the required documents.</li>
              <li>Take the entrance examination, if required.</li>
              <li>Wait for the admission confirmation.</li>
            </ul>
          </div>

          <div>
            <h3>Requirements</h3>
            <ul>
              <li>Senior High School report card.</li>
              <li>Certificate of Good Moral Character.</li>
              <li>PSA Birth Certificate copy.</li>
              <li>Recent ID pictures.</li>
            </ul>
          </div>

          <div>
            <h3>Programs Offered</h3>
            <ul>
              <li>BS Computer Science</li>
              <li>BS Information Technology</li>
              <li>BS Business Administration</li>
              <li>BS Education</li>
              <li>BS Nursing</li>
            </ul>
          </div>
        </div>

        <p class="fine-print">
          Admission requirements may vary depending on the program.
          Please confirm the official requirements with the university.
        </p>
      </section>

      <section class="card" id="tuition">
        <h2>Tuition Fee Calculator</h2>

        <p class="muted">
          Select your program, year level, units, and payment terms
          to estimate your school fees.
        </p>

        <div class="form-grid">
          <label class="field">
            <span>Program</span>
            <select v-model="program">
              <option>BS Computer Science</option>
              <option>BS Information Technology</option>
              <option>BS Business Administration</option>
              <option>BS Education</option>
              <option>BS Nursing</option>
            </select>
          </label>

          <label class="field">
            <span>Year Level</span>
            <select v-model="year">
              <option>1st Year</option>
              <option>2nd Year</option>
              <option>3rd Year</option>
              <option>4th Year</option>
            </select>
          </label>

          <label class="field">
            <span>Units This Semester: {{ units }}</span>
            <input
              v-model.number="units"
              type="range"
              min="12"
              max="27"
            />
            <div class="range-labels">
              <span>12 units</span>
              <span>27 units</span>
            </div>
          </label>
        </div>

        <div class="payment-terms">
          <span>Payment Terms</span>

          <div class="button-group">
            <button
              type="button"
              class="pill"
              :class="{ active: payment === 'Full' }"
              @click="payment = 'Full'"
            >
              Full Payment
            </button>

            <button
              type="button"
              class="pill"
              :class="{ active: payment === '3' }"
              @click="payment = '3'"
            >
              3 Installments
            </button>

            <button
              type="button"
              class="pill"
              :class="{ active: payment === '5' }"
              @click="payment = '5'"
            >
              5 Installments
            </button>
          </div>
        </div>

        <div class="table-wrap">
          <table>
            <thead>
              <tr>
                <th>Schedule of Fees</th>
                <th class="align-right">Amount</th>
              </tr>
            </thead>

            <tbody>
              <tr>
                <td>Tuition Fee ({{ units }} units × ₱650)</td>
                <td class="align-right">{{ money(tuitionFee) }}</td>
              </tr>

              <tr>
                <td>Laboratory Fee ({{ units }} units × ₱150)</td>
                <td class="align-right">{{ money(laboratoryFee) }}</td>
              </tr>

              <tr>
                <td>Miscellaneous Fee (8% of tuition)</td>
                <td class="align-right">{{ money(miscFee) }}</td>
              </tr>

              <tr class="muted-row">
                <td>Registration Fee</td>
                <td class="align-right">{{ money(750) }}</td>
              </tr>

              <tr class="muted-row">
                <td>Library Fee</td>
                <td class="align-right">{{ money(500) }}</td>
              </tr>

              <tr class="muted-row">
                <td>Athletic Fee</td>
                <td class="align-right">{{ money(350) }}</td>
              </tr>

              <tr class="muted-row">
                <td>Medical & Dental Fee</td>
                <td class="align-right">{{ money(400) }}</td>
              </tr>

              <tr class="muted-row">
                <td>Guidance & Testing Fee</td>
                <td class="align-right">{{ money(300) }}</td>
              </tr>

              <tr class="muted-row">
                <td>ID & Insurance Fee</td>
                <td class="align-right">{{ money(450) }}</td>
              </tr>

              <tr class="muted-row">
                <td>Student Organization Fee</td>
                <td class="align-right">{{ money(250) }}</td>
              </tr>
            </tbody>

            <tfoot>
              <tr class="total-row">
                <td>Total Assessment ({{ year }})</td>
                <td class="align-right">{{ money(totalFee) }}</td>
              </tr>
            </tfoot>
          </table>
        </div>

        <div class="payment-summary">
          <p>
            <strong>Selected Program:</strong> {{ program }}
          </p>
          <p>
            <strong>Payment Method:</strong>
            {{ payment === 'Full' ? 'Full Payment' : payment + ' Installments' }}
          </p>
          <p>
            <strong>Estimated Payment Per Schedule:</strong>
            {{ money(installmentAmount) }}
          </p>
        </div>

        <p class="fine-print">
          Note: All fees are sample figures for demonstration purposes only.
          Actual tuition and other charges may vary by program and year level.
        </p>
      </section>

      <section class="cta">
        <h2>Your Future Starts Here</h2>
        <p>Take the first step toward your academic goals.</p>
        <button class="primary-btn" @click="scrollToFees">
          Start Your Application
        </button>
      </section>
    </main>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const program = ref('BS Computer Science')
const year = ref('1st Year')
const units = ref(21)
const payment = ref('Full')

const tuitionFee = computed(() => units.value * 650)
const laboratoryFee = computed(() => units.value * 150)
const miscFee = computed(() => tuitionFee.value * 0.08)

const totalFee = computed(() => {
  return (
    tuitionFee.value +
    laboratoryFee.value +
    miscFee.value +
    750 +
    500 +
    350 +
    400 +
    300 +
    450 +
    250
  )
})

const installmentAmount = computed(() => {
  const count = payment.value === 'Full' ? 1 : Number(payment.value)
  return Math.ceil(totalFee.value / count * 100) / 100
})

function money(amount) {
  return new Intl.NumberFormat('en-PH', {
    style: 'currency',
    currency: 'PHP',
    maximumFractionDigits: 2
  }).format(amount)
}

function scrollToFees() {
  document.getElementById('tuition')?.scrollIntoView({
    behavior: 'smooth'
  })
}
</script>

<style scoped>
* {
  box-sizing: border-box;
}

.page {
  min-height: 100vh;
  background: #f4f8fc;
  color: #1e293b;
  font-family: Arial, Helvetica, sans-serif;
}

.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 24px;
}

/* Hero */
.hero {
  background: linear-gradient(135deg, #003366, #0056b3);
  color: #ffffff;
  padding: 65px 0;
}

.eyebrow {
  color: #bfdbfe;
  font-size: 13px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 2px;
  margin: 0 0 12px;
}

.hero h1 {
  font-size: 40px;
  line-height: 1.2;
  margin: 0 0 16px;
}

.lead {
  max-width: 650px;
  color: #e0edff;
  line-height: 1.8;
  margin-bottom: 26px;
}

/* Main */
.main {
  padding-top: 40px;
  padding-bottom: 20px;
}

.card {
  background: #ffffff;
  border: 1px solid #dbe7f5;
  border-radius: 12px;
  padding: 28px;
  margin-bottom: 26px;
  box-shadow: 0 4px 15px rgba(0, 51, 102, 0.04);
}

.card h2 {
  font-size: 25px;
  color: #003366;
  margin: 0 0 18px;
}

.muted {
  color: #64748b;
  line-height: 1.6;
}

/* Requirements */
.requirements-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 24px;
}

.requirements-grid h3 {
  color: #0056b3;
  font-size: 17px;
}

.requirements-grid ul {
  padding-left: 20px;
  color: #475569;
  line-height: 1.9;
}

/* Form */
.form-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 20px;
  margin-top: 24px;
}

.field {
  display: block;
  font-size: 14px;
}

.field span {
  display: block;
  font-weight: 600;
  margin-bottom: 10px;
  color: #1e3a5f;
}

select {
  width: 100%;
  padding: 12px;
  border: 1px solid #bfcee0;
  border-radius: 6px;
  background: #ffffff;
  color: #1e293b;
  font-size: 14px;
}

select:focus {
  outline: 2px solid #93c5fd;
  border-color: #0056b3;
}

input[type="range"] {
  width: 100%;
  accent-color: #0056b3;
  margin-top: 12px;
}

.range-labels {
  display: flex;
  justify-content: space-between;
  font-size: 12px;
  color: #64748b;
  margin-top: 5px;
}

/* Payment */
.payment-terms {
  margin: 28px 0 22px;
}

.payment-terms > span {
  display: block;
  font-weight: 700;
  color: #1e3a5f;
  margin-bottom: 12px;
}

.button-group {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
}

.pill {
  padding: 10px 16px;
  border-radius: 6px;
  font-size: 14px;
  border: 1px solid #bfcee0;
  background: #ffffff;
  color: #334155;
  cursor: pointer;
}

.pill:hover {
  border-color: #0056b3;
}

.pill.active {
  background: #0056b3;
  border-color: #0056b3;
  color: #ffffff;
}

/* Table */
.table-wrap {
  border: 1px solid #dbe7f5;
  border-radius: 8px;
  overflow-x: auto;
}

table {
  width: 100%;
  border-collapse: collapse;
  font-size: 14px;
  min-width: 350px;
}

thead {
  background: #eaf2fc;
  color: #003366;
  text-transform: uppercase;
  font-size: 12px;
}

th,
td {
  padding: 13px 16px;
  text-align: left;
}

tbody tr {
  border-top: 1px solid #edf2f7;
}

.align-right {
  text-align: right;
  white-space: nowrap;
}

.muted-row {
  color: #64748b;
}

.total-row {
  background: #eaf2fc;
  border-top: 2px solid #b8d4f5;
  color: #003366;
  font-weight: 700;
}

/* Payment summary */
.payment-summary {
  margin-top: 20px;
  padding: 18px;
  background: #f0f6ff;
  border-left: 4px solid #0056b3;
  border-radius: 6px;
}

.payment-summary p {
  margin: 8px 0;
  color: #334155;
  overflow-wrap: anywhere;
}

.fine-print {
  font-size: 12px;
  color: #64748b;
  line-height: 1.6;
  margin: 16px 0 0;
}

/* Buttons */
.primary-btn {
  display: inline-block;
  background: #0056b3;
  color: #ffffff;
  border: none;
  padding: 13px 24px;
  border-radius: 6px;
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.2s ease;
}

.primary-btn:hover {
  background: #003366;
}

.cta {
  text-align: center;
  padding: 30px 0 50px;
}

.cta h2 {
  color: #003366;
  font-size: 28px;
}

.cta p {
  color: #64748b;
  margin-bottom: 22px;
}

/* Responsive */
@media (max-width: 800px) {
  .requirements-grid,
  .form-grid {
    grid-template-columns: 1fr;
  }

  .hero h1 {
    font-size: 32px;
  }

  .card {
    padding: 20px;
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 16px;
  }

  .hero {
    padding: 45px 0;
  }

  .hero h1 {
    font-size: 28px;
  }

  .button-group {
    flex-direction: column;
  }

  .pill {
    width: 100%;
  }
}
</style>
