# 55<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1"/>
<title>Complete Business Platform</title>
<style>
body {margin:0; background:#20242b; font-family:'Segoe UI', Arial, sans-serif; color:#fff;}
header {background:#141b29; padding:24px 0; font-size:2.3rem; font-weight:700; letter-spacing:2px; text-align:center; color:#00e1ff; text-shadow:0 0 20px #0fccfc;}
nav {display:flex; justify-content: center; gap:14px; padding:10px 0; background:#141b29; border-bottom:2px solid #00e1ff;}
nav button {background:none; border:2.5px solid #0fccfc; border-radius:10px; color:#0fccfc; cursor:pointer; font-weight:700; padding:11px 22px; font-size:1rem; transition:all 0.3s ease;}
nav button:hover {background:#0fccfc; color:#202733;}
main {max-width:1100px; margin:30px auto 60px; padding:0 20px;}
.dashboard {display:grid; grid-template-columns:repeat(auto-fit,minmax(260px,1fr)); gap:40px 45px; margin-top:40px;}
.folder-card, .service-card, .category-card {background:#23273b; border:3px solid #ffe27f; border-radius:18px; padding:46px 30px; font-weight:700; font-size:1.3em; cursor:pointer; color:#ffe27f; box-shadow:0 0 22px 6px #ffe27fab,0 6px 38px #141a2ea0; text-align:center; user-select:none; transition:all 0.3s ease; min-width:240px;}
.folder-card:hover, .service-card:hover, .category-card:hover {background:#ffe27f; color:#222a39; border-color:#00e1ff; box-shadow:0 0 42px 13px #00e1ffcc,0 8px 42px #23536fab; font-weight:900; transform:scale(1.07);}
.section-title {color:#ffe27f; font-size:1.9rem; font-weight:700; margin-bottom:36px; text-align:center; text-shadow:0 0 24px #ffe27fcd;}
.service-list, .events-categories {display:grid; grid-template-columns:repeat(auto-fit,minmax(210px,1fr)); gap:28px 34px; justify-content:center; margin-top:22px; margin-bottom:42px;}
form.contact-form {background:#172440; border:2px solid #00e1ff88; border-radius:18px; color:#afdfff; font-size:1.12em; margin:22px auto 60px; max-width:480px; padding:36px 40px;}
form.contact-form label {display:block; margin-bottom:10px; font-weight:700; color:#8ec7ff;}
form.contact-form input, form.contact-form textarea, form.contact-form select {width:100%; background:#0f1f3a; border:1.8px solid #38abf7; border-radius:10px; padding:15px 20px; margin-bottom:26px; font-size:16px; color:#cde4ff; box-sizing:border-box; outline:none; resize:vertical;}
form.contact-form input:focus, form.contact-form textarea:focus, form.contact-form select:focus {background:#1959ba; border-color:#00aeff;}
form.contact-form button {width:100%; padding:18px 0; font-weight:900; font-size:1.28em; border:none; border-radius:15px; background:#00e1ff; color:#192b3a; cursor:pointer; transition:background-color 0.3s ease;}
form.contact-form button:hover {background:#3de1ff;}
.back-btn {background:#ffe27f; border-radius:16px; font-weight:900; font-size:1.25em; border:3px solid #ffe27f; padding:20px 70px; margin:35px auto 20px; cursor:pointer; transition:all 0.3s ease;}
.back-btn:hover {background:#00e1ff; border-color:#00e1ff; color:#fff; box-shadow:0 0 42px 18px #00e1ffcc;}
video#video {max-width:100%; border-radius:15px; border:2px solid #00e1ff8f; margin-top:28px;}
#map {max-width:640px; height:460px; border-radius:15px; margin:28px auto 56px; border:3px solid #00e1ff94; box-shadow:0 0 36px 18px #00e1ff52;}
#photoOutput img {max-width:320px; border-radius:16px;}
@media(max-width:900px){.dashboard, .service-list, .events-categories{grid-template-columns:1fr; gap:26px;}}
</style>
</head>
<body>

<header>JKS Group of Business</header>

<nav>
  <button onclick="showPage('dashboard')">Dashboard</button>
  <button onclick="showPage('profile')">Profile</button>
  <button onclick="showPage('wallet')">Wallet</button>
  <button onclick="showPage('orders')">Orders</button>
  <button onclick="showPage('camera')">Camera</button>
  <button onclick="showPage('maps')">Google Maps</button>
  <button onclick="showPage('recharge')">Recharge & Bills</button>
</nav>

<main>
  <!-- Dashboard with modules -->
  <section id="dashboard" class="dashboard"></section>

  <!-- Profile -->
  <section id="profile" style="display:none;">
    <h2 class="section-title">Profile</h2>
    <form class="contact-form">
      <label>Name:</label><input id="profileName" type="text" />
      <label>Email:</label><input id="profileEmail" type="email" />
      <label>Phone:</label><input id="profilePhone" type="tel" />
      <label>Address:</label><textarea id="profileAddress" rows="3"></textarea>
      <button type="button" onclick="alert('Profile updated!')">Save</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back</button>
  </section>

  <!-- Wallet -->
  <section id="wallet" style="display:none;">
    <h2 class="section-title">Wallet</h2>
    <p>Balance: ₹<span id="walletBalance">10000</span></p>
    <form class="contact-form" onsubmit="addMoney(event)">
      <label>Add Money:</label>
      <input id="addMoney" type="number" min="1" required />
      <button type="submit">Add Funds</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back</button>
  </section>

  <!-- Orders -->
  <section id="orders" style="display:none;">
    <h2 class="section-title">Orders</h2>
    <table style="width:100%; border-collapse:collapse; background:#1c2238; color:#fff; border-radius:8px;">
      <thead><tr><th style="padding:14px;">Order ID</th><th>Product/Service</th><th>Status</th></tr></thead>
      <tbody>
        <tr><td>001</td><td>Pizza</td><td style="color:#3eff9d;">Delivered</td></tr>
        <tr><td>002</td><td>Car Wash</td><td style="color:#ffe27f;">Pending</td></tr>
        <tr><td>003</td><td>Loan</td><td style="color:#0bcfff;">In Progress</td></tr>
      </tbody>
    </table>
    <button class="back-btn" onclick="showPage('dashboard')">Back</button>
  </section>

  <!-- Service View -->
  <section id="serviceView" style="display:none; flex-direction:column; align-items:center;">
    <h2 class="section-title" id="serviceTitle"></h2>
    <div class="service-list" id="serviceList"></div>
    <form class="contact-form" id="contactForm" style="display:none;">
      <label>Name:</label><input id="svcName" type="text" required />
      <label>Mobile:</label><input id="svcPhone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required />
      <label>Message:</label><textarea id="svcMessage" rows="4" required></textarea>
      <button type="button" onclick="sendWhatsApp()">Send to WhatsApp</button>
      <button class="back-btn" onclick="backToServices()">Back</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back</button>
  </section>

  <!-- Events & Catering -->
  <section id="events" style="display:none; flex-direction:column; align-items:center;">
    <h2 class="section-title" id="eventsCatTitle"></h2>
    <div class="events-categories" id="eventsCategories"></div>
    <div class="service-list" id="eventsServiceList"></div>
    <form id="eventForm" class="contact-form" style="display:none;">
      <label>Name:</label><input id="eventName" type="text" required />
      <label>Mobile:</label><input id="eventPhone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required />
      <div id="eventExtra"></div>
      <label>Message:</label><textarea id="eventMsg" rows="4" required></textarea>
      <button type="button" onclick="sendWhatsApp()">Send to WhatsApp</button>
      <button class="back-btn" onclick="backToEvents()">Back</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back</button>
  </section>

  <!-- E-commerce -->
  <section id="ecommerce" style="display:none; flex-direction:column; align-items:center;">
    <h2 class="section-title">My E-commerce</h2>
    <div style="display:flex; gap:12px; margin-bottom:18px; justify-content:center;">
      <button onclick="openEcomCategory('Groceries')">Groceries</button>
      <button onclick="openEcomCategory('Food')">Food</button>
      <button onclick="openEcomCategory('Pharmacy')">Pharmacy</button>
    </div>
    <div class="service-list" id="ecomServices"></div>
    <form id="ecomOrderForm" class="contact-form" style="display:none;">
      <h3 id="ecomOrderTitle"></h3>
      <label>Name:</label><input name="name" type="text" required />
      <label>Mobile:</label><input name="phone" pattern="[6-9][0-9]{9}" maxlength="10" type="tel" required />
      <label>Order Details:</label><textarea name="orderDetails" rows="3" required></textarea>
      <label>Address:</label><textarea name="address" required></textarea>
      <button type="submit">Order via WhatsApp</button>
      <button type="button" class="back-btn" onclick="backToEcom()">Back</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back</button>
  </section>

  <!-- Recharge & Bills -->
  <section id="recharge" style="display:none; flex-direction:column; align-items:center;">
    <h2 class="section-title">Recharge & Bills</h2>
    <div style="display:flex; gap:12px; margin-bottom:18px; justify-content:center;">
      <button onclick="openRechargeCategory('Mobile')">Mobile</button>
      <button onclick="openRechargeCategory('DTH')">DTH</button>
      <button onclick="openRechargeCategory('Electricity')">Electricity</button>
      <button onclick="openRechargeCategory('Water')">Water</button>
      <button onclick="openRechargeCategory('Gas')">Gas</button>
    </div>
    <div class="service-list" id="rechargeServices"></div>
    <form id="rechargeForm" class="contact-form" style="display:none;">
      <h3 id="rechargeTitle"></h3>
      <label>Name:</label><input id="rname" type="text" required />
      <label>Mobile:</label><input id="rphone" pattern="[6-9][0-9]{9}" maxlength="10" type="tel" required />
      <label>Details:</label><textarea id="rdetails" rows="3" required></textarea>
      <label>Address (if applicable):</label><textarea id="raddress"></textarea>
      <button type="button" onclick="sendWhatsApp()">Pay & Confirm</button>
      <button class="back-btn" onclick="backToRecharge()">Back</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back</button>
  </section>

  <!-- Camera -->
  <section id="camera" style="display:none;">
    <h2 class="section-title">Camera</h2>
    <video id="video" autoplay muted playsinline></video>
    <div style="margin:20px 0;">
      <button onclick="switchCamera()">Switch Camera</button>
      <button onclick="capturePhoto()">Capture Photo</button>
    </div>
    <canvas id="canvas"></canvas>
    <div id="photoOutput"></div>
    <button class="back-btn" onclick="showPage('dashboard')">Back</button>
  </section>

  <!-- Google Maps -->
  <section id="maps" style="display:none;">
    <h2 class="section-title">Google Maps</h2>
    <iframe
      width="100%" height="460" style="border:0; border-radius:14px; margin:28px auto 52px; box-shadow:0 0 36px 18px #00e1ff52;"
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3806.272668041566!2d78.48261611487654!3d17.385044788065196!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3bcb9736285f645f%3A0xf4dae048bfe79116!2sHyderabad!5e0!3m2!1sen!2sin!4v1633072783551!5m2!1sen!2sin"
      allowfullscreen="" loading="lazy"></iframe>
    <button class="back-btn" onclick="showPage('dashboard')">Back</button>
  </section>
</main>

<script>
const folders = [
  { id: 'ecommerce', label: 'My E-commerce' },
  { id: 'events', label: 'Events & Catering' },
  { id: 'courier', label: 'Courier & Ride Booking' },
  { id: 'job', label: 'Job Consultancy & Services' },
  { id: 'tours', label: 'Tours & Travels' },
  { id: 'realestate', label: 'Real Estate & Construction' },
  { id: 'investment', label: 'Investment & Business' },
  { id: 'loans', label: 'Loans & Insurance' },
  { id: 'home', label: 'Home Services' },
  { id: 'recharge', label: 'Recharge & Bills' }
];

const moduleServices = {
  courier: ['Courier Booking', 'Ride Booking', 'Tracking', 'Support', 'Rental Vehicles'],
  job: ['Job Search', 'Post Resume', 'Local Jobs', 'Non-Local Jobs', 'PG & Hostel', 'Services Marketplace'],
  tours: ['Tour Bookings', 'Custom & Regular Tours', 'Stay Booking', 'Vehicle Booking', 'Train/Bus/Flight Tickets'],
  realestate: ['Buy', 'Sell', 'Rent', 'Key Services', 'Construction', 'Industry'],
  investment: ['Gold', 'Silver', 'Real Estate', 'Business Opportunity', 'Mutual Funds'],
  loans: ['Loan Enquiry', 'Car Insurance', 'Bike Insurance', 'Housing Loans', 'Personal Loans', 'Health Insurance'],
  home: ['CC Camera Installation', 'Computer Repair', 'Car Wash', 'Mobile Repair', 'Chef Services', 'Bouncers', 'Bike Mechanic', 'Car Mechanic', 'Electrician', 'Painter', 'Plumber', 'Driver']
};

const ecom = {
  Groceries: ['Milk', 'Meat', 'Fruits', 'Vegetables', 'Flowers', 'Others'],
  Food: ['Biriyani', 'Tiffins', 'Ice Cream', 'Pizza', 'Burgers', 'Rolls'],
  Pharmacy: ['Medicines', 'Health Products', 'Supplements', 'Care Products']
};

const eventsCategories = {
  package: [
    { name: 'Silver', amount: '50k - 160k' },
    { name: 'Gold', amount: '150k - 300k' },
    { name: 'Diamond', amount: '500k - 5M' },
    { name: 'Platinum', amount: '500k - 800k' }
  ],
  customized: [
    'Decoration', 'Catering', 'Photography & Videography', 'Anchor & Actors', 'DJ & Singers', 'Guest House', 'Chocolate & Cake', 'Games & Entertainment', 'Jewellery', 'Invitation Cards', 'Vehicles', 'Return Gifts', 'Makeup Artist', 'Mehandi Artist', 'Clothing & Accessories'
  ],
  premium: [
    'Decoration', 'Catering', 'Photography & Videography', 'Anchor & Actors', 'DJ & Singers', 'Guest House', 'Chocolate & Cake', 'Games & Entertainment', 'Jewellery', 'Invitation Cards', 'Vehicles', 'Return Gifts', 'Makeup Artist', 'Mehandi Artist', 'Clothing & Accessories'
  ]
};

const rechargeServices = ['Mobile Recharge', 'DTH Recharge', 'Electricity Bill', 'Water Bill', 'Gas Bill'];

let currentPage = '';

function showPage(page){
  document.querySelectorAll('section').forEach(s=>s.style.display='none');
  document.getElementById(page).style.display='block';
  if(page==='dashboard') renderDashboard();
  if(page==='recharge') openRecharge();
  if(page==='maps') initMap();
  // Other views are just toggled
}

// Utility to render the main dashboard with modules
function renderDashboard() {
  const dash = document.getElementById('dashboard');
  dash.innerHTML='';
  folders.forEach(f=>{
    const c=document.createElement('div');
    c.className='folder-card';
    c.innerText= f.label;
    c.onclick=()=>openModule(f.id);
    dash.appendChild(c);
  });
}

function openModule(id) {
  currentPage=id;
  // Reset views
  document.querySelectorAll('section').forEach(s=>s.style.display='none');
  if(id==='ecommerce') { openEcom(); return; }
  if(id==='events') { openEvents(); return; }
  if(id==='recharge') { openRecharge(); return; }
  // For other modules, list services
  const list = document.getElementById('serviceList');
  list.innerHTML='';
  (moduleServices[id]||[]).forEach(svc=>{
    const d=document.createElement('div');
    d.className='service-card';
    d.innerText=svc;
    d.onclick= ()=>openContactForm(svc);
    list.appendChild(d);
  });
  document.getElementById('serviceTitle').innerText=folders.find(f=>f.id===id).label;
  document.getElementById('serviceView').style.display='block';
}

function openContactForm(service){
// Show contact form with WhatsApp message logic
  document.getElementById('serviceList').style.display='none';
  const form=document.getElementById('contactForm');
  form.style.display='block';
  document.getElementById('contactTitle').innerText='Contact for '+service;
  clearInputs(['userName','userPhone','userMessage']);
  // Store for WhatsApp message
  form.setAttribute('data-service',service);
}

function backToServices() {
  document.getElementById('contactForm').style.display='none';
  document.getElementById('serviceList').style.display='grid';
}

function submitWhatsApp(){
  const service=document.getElementById('contactForm').getAttribute('data-service');
  const name=document.getElementById('userName').value.trim();
  const phone=document.getElementById('userPhone').value.trim();
  const msg=document.getElementById('userMessage').value.trim();
  if(!name || !phone || !msg){ alert('Fill all'); return;}
  const txt= `Name: ${encodeURIComponent(name)}%0APhone: ${encodeURIComponent(phone)}%0AService: ${encodeURIComponent(service)}%0AMsg: ${encodeURIComponent(msg)}`;
  // only WhatsApp API
  window.open(`https://api.whatsapp.com/send?phone=918977143043&text=${txt}`,'_blank');
}

function clearInputs(ids){
  ids.forEach(i=>{
    const e=document.getElementById(i);
    e.value='';
  });
}

// Events
function openEvents() {
  document.getElementById('dashboard').style.display='none';
  document.getElementById('serviceView').style.display='none';
  document.getElementById('ecomView').style.display='none';
  document.getElementById('recharge').style.display='none';
  document.getElementById('events').style.display='flex';
  const catDiv=document.getElementById('eventsCategories');
  catDiv.innerHTML='';
  ['package','customized','premium'].forEach(c => {
    const d=document.createElement('div');
    d.className='category-card';
    d.innerText=c.charAt(0).toUpperCase()+ c.slice(1);
    d.onclick=()=>openEventCategory(c);
    catDiv.appendChild(d);
  });
  document.getElementById('eventsServiceList').innerHTML='';
  document.getElementById('eventForm').style.display='none';
  document.getElementById('eventsCategoryTitle').innerText='Event Types';
}

function openEventCategory(cat){
  currentEventCat=cat;
  document.getElementById('eventsServiceList').style.display='grid';
  document.getElementById('eventsServiceList').innerHTML='';
  if(cat==='package'){
    eventsCategories.package.forEach(p=>{
      const d=document.createElement('div');
      d.className='service-card';
      d.innerText= p.name+' ('+p.amount+')';
      d.onclick= ()=>openEventContact(p.name);
      this.appendChild(d);
    });
  }else{
    eventsCategories[cat].forEach(s=>{
      const d=document.createElement('div');
      d.className='service-card';
      d.innerText=s;
      d.onclick= ()=>openEventContact(s);
      this.appendChild(d);
    });
  }
  document.getElementById('eventsCategoryTitle').innerText=cat.charAt(0).toUpperCase()+cat.slice(1)+' Services';
}
function openEventContact(svc){
  currentEventService=svc;
  document.getElementById('eventsServiceList').style.display='none';
  const form=document.getElementById('eventForm');
  form.style.display='block';
  document.getElementById('eventsContactTitle').innerText='Contact for '+svc;
  document.getElementById('eventsUserName').value='';
  document.getElementById('eventsUserPhone').value='';
  document.getElementById('eventsUserMessage').value='';
  document.getElementById('customFields').innerHTML='';
  if(currentEventCat==='customized'){
    document.getElementById('customFields').innerHTML=`
      <label>Budget:</label>
      <select id='eventsBudget' required><option value=''>Select Budget</option>
        <option>10k to 50k</option>
        <option>50k to 1L</option>
        <option>1L to 5L</option>
        <option>5L to 10L</option>
        <option>Above 10L</option>
      </select>
      <label>Capacity:</label>
      <select id='eventsCapacity' required><option value=''>Select Capacity</option>
        <option>5-30 people</option>
        <option>30-60 people</option>
        <option>60-90 people</option>
        <option>90-130 people</option>
        <option>Above 130 people</option>
      </select>`;
  }
}
function backToEvents(){
  document.getElementById('eventForm').style.display='none';
  document.getElementById('eventsServiceList').style.display='grid';
}
function submitEvents() {
  const n=document.getElementById('eventsUserName').value.trim();
  const p=document.getElementById('eventsUserPhone').value.trim();
  const msg=document.getElementById('eventsUserMessage').value.trim();
  const budget=document.getElementById('eventsBudget')?.value;
  const capacity=document.getElementById('eventsCapacity')?.value;
  if(!n||!p||!msg){ alert('Fill all'); return;}
  let m= `Name: ${encodeURIComponent(n)}%0APhone: ${encodeURIComponent(p)}%0AService: ${encodeURIComponent(currentEventService)}%0AType: ${encodeURIComponent(currentEventCat)}%0AMsg: ${encodeURIComponent(msg)}`;
  if(budget) m+= `%0ABudget: ${encodeURIComponent(budget)}`;
  if(capacity) m+= `%0ACapacity: ${encodeURIComponent(capacity)}`;
  window.open(`https://api.whatsapp.com/send?phone=918977143043&text=${m}`,'_blank');
}

// E-commerce
function openEcom() {
  document.getElementById('dashboard').style.display='none';
  document.getElementById('serviceView').style.display='none';
  document.getElementById('events').style.display='none';
  document.getElementById('recharge').style.display='none';
  document.getElementById('ecommerce').style.display='flex';
  document.getElementById('ecomServices').innerHTML='';  
}
function openEcomCategory(cat){
  document.getElementById('ecomServices').innerHTML='';
  (ecom[cat]||[]).forEach(s=>{
    const d=document.createElement('div');
    d.className='service-card';
    d.innerText=s;
    d.onclick=()=>openEcomOrder(s,cat);
    document.getElementById('ecomServices').appendChild(d);
  });
}
function openEcomOrder(svc,cat){
  document.getElementById('ecomOrderForm').style.display='block';
  document.getElementById('ecomOrderTitle').innerText=`Order ${svc} in ${cat}`;
  document.getElementById('ecomOrderForm').onsubmit=function(e){
    e.preventDefault();
    const n=document.querySelector('input[name="name"]').value.trim();
    const p=document.querySelector('input[name="phone"]').value.trim();
    const d=document.querySelector('textarea[name="orderDetails"]').value.trim();
    const a=document.querySelector('textarea[name="address"]').value.trim();
    if(!n||!p||!d||!a){ alert('Fill'); return;}
    const msg=`Order: ${encodeURIComponent(svc)}%0AName: ${encodeURIComponent(n)}%0APhone: ${encodeURIComponent(p)}%0ADetails: ${encodeURIComponent(d)}%0AAddress: ${encodeURIComponent(a)}`;
    window.open(`https://api.whatsapp.com/send?phone=918977143043&text=${msg}`,'_blank');
  };
}
function backToEcom(){ document.getElementById('ecomOrderForm').style.display='none';}

// Recharge Bills
function openRecharge(){
  document.getElementById('dashboard').style.display='none';
  document.getElementById('serviceView').style.display='none';
  document.getElementById('events').style.display='none';
  document.getElementById('ecommerce').style.display='none';
  document.getElementById('recharge').style.display='flex';
  document.getElementById('rechargeServices').innerHTML='';
}
function openRechargeCategory(cat){
  document.getElementById('rechargeServices').innerHTML='';
  rechargeServices.forEach(s=>{
    if(cat==='Mobile' && (s==='DTH' || s==='Electricity' || s==='Water' || s==='Gas')){
      const d=document.createElement('div');
      d.className='service-card';
      d.innerText=s;
      d.onclick=()=>setRecharge(s,cat);
      document.getElementById('rechargeServices').appendChild(d);
    }
  });
}
function setRecharge(s,cat){
  document.getElementById('rechargeForm').style.display='block';
  document.getElementById('rechargeTitle').innerText=`Pay ${s}`;
  document.querySelector('form#rechargeForm').onsubmit=function(e){
    e.preventDefault();
    const n=document.querySelector('#rname').value.trim();
    const p=document.querySelector('#rphone').value.trim();
    const d=document.querySelector('#rdetails').value.trim();
    const a=document.querySelector('#raddress').value.trim();
    if(!n||!p||!d){ alert('Fill all'); return;}
    const msg=`Recharge Bills: ${encodeURIComponent(s)}%0AName: ${encodeURIComponent(n)}%0APhone: ${encodeURIComponent(p)}%0ADetails: ${encodeURIComponent(d)}%0AAddress: ${encodeURIComponent(a)}`;
    window.open(`https://api.whatsapp.com/send?phone=918977143043&text=${msg}`,'_blank');
  }
}
function backToRecharge(){ document.getElementById('rechargeForm').style.display='none'; }

function showPage(page) {
  document.querySelectorAll('section').forEach(s=>s.style.display='none');
  document.getElementById(page).style.display='block';
  if(page==='dashboard') renderDashboard();
  if(page==='maps') initMap();
  if(page==='recharge') { openRecharge(); }
}
function renderDashboard() {
  const d=document.getElementById('dashboard');
  d.innerHTML='';
  folders.forEach(f=>{
    const c=document.createElement('div');
    c.className='folder-card';
    c.innerText=f.label;
    c.onclick=()=>openModule(f.id);
    d.appendChild(c);
  });
}


// Camera
let stream=null;
let front=true;
function startCamera(){
  if(stream) stream.getTracks().forEach(t=>t.stop());
  navigator.mediaDevices.getUserMedia({video:{facingMode:front?'user':'environment'}})
  .then(s=>{
    stream=s;
    document.querySelector('#video').srcObject=s;
  })
  .catch(()=>alert('Camera not supported or denied'));
}
function switchCamera(){ front=!front; startCamera(); }
function capturePhoto(){
  const c=document.createElement('canvas');
  c.width=document.querySelector('#video').videoWidth;
  c.height=document.querySelector('#video').videoHeight;
  c.getContext('2d').drawImage(document.querySelector('#video'),0,0);
  document.getElementById('photoOutput').innerHTML=`<img src="${c.toDataURL()}" />`;
}
</script>
<script>
const folders=[
  {id:'ecommerce',label:'My E-commerce'},
  {id:'events',label:'Events & Catering'},
  {id:'courier',label:'Courier & Ride Booking'},
  {id:'job',label:'Job Consultancy & Services'},
  {id:'tours',label:'Tours & Travels'},
  {id:'realestate',label:'Real Estate & Construction'},
  {id:'investment',label:'Investment & Business'},
  {id:'loans',label:'Loans & Insurance'},
  {id:'home',label:'Home Services'},
  {id:'recharge',label:'Recharge & Bills'}
];


renderDashboard();

</script>
</body>
</html>
