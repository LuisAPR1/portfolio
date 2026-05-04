---
title: "Resume"
description: "MSc Computer Science student at IST. Distributed systems, machine learning, data engineering, and full-stack web."
---

<h1 class="mb-0">Resume</h1>
<p class="mt-1 text-gray-400 mb-4">A summary of my background, education, and professional experience. A Latex and full PDF version are available below.</p>

<div class="custom flex gap-3 flex-wrap justify-center" style="margin-top:2.5rem;margin-bottom:4rem;">
  <a class="custom inline-block group" href="{{< u "/cv.pdf" >}}" target="_blank">
    <button class="custom flex items-center gap-3 font-semibold text-white bg-transparent border border-[#27272a] rounded-md backdrop-blur-sm focus:outline-none focus:ring-2 focus:ring-white/60 cursor-pointer" style="padding:0.85rem 1.4rem;font-size:1.05rem;">
      Download PDF
      <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentcolor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15v4a2 2 0 01-2 2H5a2 2 0 01-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>
    </button>
  </a>
  <a class="custom inline-block group" href="{{< u "/cv.tex" >}}" target="_blank">
    <button class="custom flex items-center gap-3 font-semibold text-white bg-transparent border border-[#27272a] rounded-md backdrop-blur-sm focus:outline-none focus:ring-2 focus:ring-white/60 cursor-pointer" style="padding:0.85rem 1.4rem;font-size:1.05rem;">
      LaTeX source
      <svg xmlns="http://www.w3.org/2000/svg" width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentcolor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>
    </button>
  </a>
</div>

<h2 id="education">Education</h2>

<div class="card">
  <div class="custom flex justify-between items-start flex-wrap gap-2">
    <div class="custom">
      <h3 class="custom" style="margin:0;color:#fff;font-size:1.5rem;font-weight:600;line-height:1.2;"><a class="custom exp-link" href="https://fenix.tecnico.ulisboa.pt/cursos/meic-t/curriculo" target="_blank" rel="noopener">Instituto Superior Técnico</a></h3>
      <p class="custom text-gray-300" style="margin:0.4rem 0 0;">Master's in Computer Science and Engineering</p>
      <p class="custom text-gray-500 text-sm" style="margin:0.25rem 0 0;">Specialization: Artificial Intelligence and Data Science</p>
    </div>
    <p class="custom text-gray-400" style="margin:0;">Sep. 2025 - Present · Lisbon, Portugal</p>
  </div>
</div>

<div class="card">
  <div class="custom flex justify-between items-start flex-wrap gap-2">
    <div class="custom">
      <h3 class="custom" style="margin:0;color:#fff;font-size:1.5rem;font-weight:600;line-height:1.2;"><a class="custom exp-link" href="https://www.ualg.pt/curso/1478" target="_blank" rel="noopener">University of Algarve</a></h3>
      <p class="custom text-gray-300" style="margin:0.4rem 0 0;">Bachelor's in Computer Engineering</p>
      <p class="custom text-gray-500 text-sm" style="margin:0.25rem 0 0;">Final grade: 15/20</p>
    </div>
    <p class="custom text-gray-400" style="margin:0;">Sep. 2022 - Jun. 2025 · Faro, Portugal</p>
  </div>
</div>

<h2 id="experience">Professional Experience</h2>

<div class="card">
  <div class="custom flex justify-between items-start flex-wrap gap-2">
    <div class="custom">
      <h3 class="custom" style="margin:0;color:#fff;font-size:1.5rem;font-weight:600;line-height:1.2;"><a class="custom exp-link" href="https://www.ds.pt/" target="_blank" rel="noopener">DigitSigma</a></h3>
      <p class="custom text-gray-300" style="margin:0.4rem 0 0;">Software &amp; Web Developer (Trainee)</p>
    </div>
    <p class="custom text-gray-400" style="margin:0;">Jul. 2022 - Aug. 2022 · Loulé, Portugal</p>
  </div>
  <ul class="custom resume-list" style="margin-top:1rem;">
    <li class="custom">Development of <strong>web applications</strong> and <strong>Windows Forms</strong> (.NET) for internal tools.</li>
    <li class="custom">Database management and implementation of full-stack features end-to-end.</li>
    <li class="custom">Stack: <strong>C#, PHP, JavaScript, HTML, Bootstrap, Axios, Ajax.</strong></li>
  </ul>
</div>

<h2 id="featured-projects">Featured Projects</h2>

<p>A selection of the highlights below. For the full project list with technical deep-dives, see <a href="{{< u "/projects/" >}}">Projects</a>.</p>

<ul class="resume-list project-list">
  <li class="custom"><strong><a href="{{< u "/projects/uk-data-warehouse/" >}}">ETL &amp; OLAP Data Warehouse Pipeline</a></strong> · End-to-end data warehousing solution with ETL processes and OLAP analytics for multidimensional analysis.</li>
  <li class="custom"><strong><a href="{{< u "/projects/depchain/" >}}">Permissioned Blockchain with BFT Consensus</a></strong> · DepChain: permissioned blockchain with HotStuff BFT consensus, EVM smart contracts, and frontrunning-resistant ERC-20 approvals.</li>
  <li class="custom"><strong><a href="{{< u "/projects/flight-cancellation-predictor/" >}}">ML Prediction Pipeline</a></strong> · End-to-end machine learning pipeline with multiple classifiers and a FastAPI interface for real-time predictions and batch evaluation.</li>
  <li class="custom"><strong><a href="{{< u "/projects/digit-recognition-nn-v2/" >}}">Digit Recognition NN V2</a></strong> · End-to-end MNIST digit recognizer with a from-scratch Java neural network and a web playground for live inference.</li>
  <li class="custom"><strong><a href="{{< u "/projects/distributed-kv-store/" >}}">Distributed Key-Value Storage System</a></strong> · Resilient architecture with FastAPI, Redis, RabbitMQ, CockroachDB, observability, and autoscaling.</li>
  <li class="custom"><strong><a href="{{< u "/projects/cinebyte/" >}}">React + TS REST API Movie App</a></strong> · Full-stack movies and TV shows app with React, TypeScript, and a Node.js REST API, powered by the TMDb API.</li>
  <li class="custom"><strong><a href="{{< u "/projects/physics-engine/" >}}">2D Physics Engine</a></strong> · Web-based 2D physics simulation built from scratch with p5.js, featuring rigid body dynamics, AABB collisions, and Verlet integration.</li>
</ul>


<h2 id="skills">Technical Skills</h2>

<ul class="resume-list">
  <li class="custom"><strong>Languages:</strong> C#, Java, Python, JavaScript, TypeScript, PHP, SQL, HTML/CSS, C/C++</li>
  <li class="custom"><strong>Frameworks &amp; libraries:</strong> React, Node.js, Express, FastAPI, .NET, Scikit-learn, Material-UI, Bootstrap</li>
  <li class="custom"><strong>Data &amp; analytics:</strong> MySQL, Pentaho (PDI / Report Designer), OLAP, MDX, ARIMA, LSTM, Pandas, NumPy, Redis, RabbitMQ, CockroachDB</li>
  <li class="custom"><strong>Infrastructure &amp; tools:</strong> Git, Docker, Nginx, Prometheus, Grafana, Arduino</li>
  <li class="custom"><strong>Spoken languages:</strong> Portuguese (Native / C2), English (B2)</li>
</ul>
