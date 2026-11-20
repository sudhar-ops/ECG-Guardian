[index (1).html](https://github.com/user-attachments/files/35158795/index.1.html)<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>ECG Guardian | MedSignal Technologies</title>

    <link rel="stylesheet" href="style.css">
</head>

<body>

    <!-- LOGIN PAGE -->
    <section id="loginPage" class="login-page">

        <div class="login-card">

            <div class="brand-logo">♡</div>

            <p class="company-name">MedSignal Technologies</p>

            <h1>ECG Guardian</h1>

            <p class="login-description">
                Intelligent ECG monitoring for biomedical engineering education.
            </p>

            <form id="loginForm">

                <label for="email">User ID</label>

                <input
                    type="text"
                    id="email"
                    placeholder="Enter user ID"
                    required
                >

                <label for="password">Password</label>

                <input
                    type="password"
                    id="password"
                    placeholder="Enter password"
                    required
                >

                <button type="submit" class="primary-button">
                    Sign In
                </button>

                <p id="loginError" class="login-error"></p>

            </form>

            <p class="login-note">
                Educational simulation • No real patient data
            </p>

        </div>

    </section>


    <!-- APPLICATION -->
    <div id="app" class="app hidden">

        <!-- SIDEBAR -->
        <aside class="sidebar">

            <div class="sidebar-brand">
                <div class="small-logo">♡</div>

                <div>
                    <h2>ECG Guardian</h2>
                    <p>MedSignal Technologies</p>
                </div>
            </div>

            <nav class="navigation">

                <button class="nav-item active" data-page="dashboardPage">
                    <span>▦</span>
                    Dashboard
                </button>

                <button class="nav-item" data-page="monitorPage">
                    <span>⌁</span>
                    ECG Monitor
                </button>

                <button class="nav-item" data-page="patientPage">
                    <span>♙</span>
                    Patient Profile
                </button>

                <button class="nav-item" data-page="troubleshootingPage">
                    <span>⚙</span>
                    Troubleshooting
                </button>

                <button class="nav-item" data-page="alarmsPage">
                    <span>!</span>
                    Alarm Center
                </button>

            </nav>

            <div class="sidebar-bottom">

                <button id="darkModeButton" class="sidebar-action">
                    ◐ Toggle Theme
                </button>

                <button id="logoutButton" class="sidebar-action logout-button">
                    ↪ Logout
                </button>

            </div>

        </aside>


        <!-- MAIN CONTENT -->
        <main class="main-content">

            <header class="topbar">

                <div>
                    <p class="topbar-label">MEDICAL MONITORING SYSTEM</p>
                    <h2 id="pageTitle">Dashboard</h2>
                </div>

                <div class="online-status">
                    <span></span>
                    System Online
                </div>

            </header>


            <!-- DASHBOARD -->
            <section id="dashboardPage" class="page">

                <div class="welcome-section">

                    <div>
                        <p class="section-label">OVERVIEW</p>

                        <h1>Welcome to ECG Guardian</h1>

                        <p class="muted">
                            Monitor simulated ECG activity from one professional workspace.
                        </p>
                    </div>

                    <button class="primary-button" data-page="monitorPage">
                        Start Monitoring
                    </button>

                </div>


                <div class="stat-grid">

                    <div class="stat-card">
                        <p>System Status</p>
                        <h2>Online</h2>
                        <span class="stat-green">Ready for simulation</span>
                    </div>

                    <div class="stat-card">
                        <p>ECG Signal</p>
                        <h2 id="dashboardHeartRate">72 BPM</h2>
                        <span class="stat-green">Simulated reading</span>
                    </div>

                    <div class="stat-card">
                        <p>Patient Record</p>
                        <h2 id="dashboardPatientName">Not Added</h2>
                        <span class="stat-muted">Educational profile</span>
                    </div>

                </div>


                <div class="dashboard-grid">

                    <div class="panel">

                        <div class="panel-heading">
                            <div>
                                <p class="section-label">LIVE PREVIEW</p>
                                <h2>ECG Waveform</h2>
                            </div>

                            <span class="badge success">Simulated</span>
                        </div>

                        <canvas id="dashboardCanvas"></canvas>

                        <button class="secondary-button" data-page="monitorPage">
                            Open Full Monitor
                        </button>

                    </div>


                    <div class="panel">

                        <div class="panel-heading">
                            <div>
                                <p class="section-label">QUICK ACCESS</p>
                                <h2>Workspace</h2>
                            </div>
                        </div>

                        <div class="quick-actions">

                            <button data-page="patientPage">
                                Patient Profile
                            </button>

                            <button data-page="troubleshootingPage">
                                Troubleshooting
                            </button>

                            <button data-page="alarmsPage">
                                Alarm Center
                            </button>

                        </div>

                    </div>

                </div>

            </section>


            <!-- ECG MONITOR -->
            <section id="monitorPage" class="page hidden">

                <div class="page-heading">

                    <div>
                        <p class="section-label">REAL-TIME SIMULATION</p>
                        <h1>ECG Monitor</h1>
                        <p class="muted">
                            Simulated ECG waveform monitoring workspace.
                        </p>
                    </div>

                    <span id="monitorStatus" class="badge success">
                        Monitoring Ready
                    </span>

                </div>


                <div class="panel">

                    <div class="monitor-topbar">

                        <div>
                            <p class="muted">Heart Rate</p>
                            <h2 id="heartRate">72 <small>BPM</small></h2>
                        </div>

                        <div>
                            <p class="muted">Signal Mode</p>
                            <h3 id="currentModeLabel">Normal Sinus Rhythm</h3>
                        </div>

                        <div>
                            <p class="muted">ECG Status</p>
                            <span id="ecgStatus" class="badge danger">
                                ● ECG OFF
                            </span>
                        </div>

                    </div>

                    <canvas id="ecgCanvas"></canvas>

                    <div class="monitor-controls">

                        <button id="startEcgButton" class="primary-button">
                            Start ECG
                        </button>

                        <button id="stopEcgButton" class="secondary-button">
                            Stop ECG
                        </button>

                        <button id="muteButton" class="secondary-button">
                            Mute Alarm
                        </button>

                    </div>


                    <div class="mode-area">

                        <label for="waveformMode">
                            ECG Simulation Mode
                        </label>

                        <select id="waveformMode">

                            <option value="normal">Normal Sinus Rhythm</option>
                            <option value="tachycardia">Tachycardia</option>
                            <option value="bradycardia">Bradycardia</option>
                            <option value="irregular">Irregular Rhythm</option>
                            <option value="noisy">Noisy Signal</option>
                            <option value="leadoff">Lead-Off</option>
                            <option value="flatline">Flatline</option>

                        </select>

                        <p id="modeInformation" class="mode-information">
                            Normal simulated sinus rhythm.
                        </p>

                    </div>

                </div>

            </section>


            <!-- PATIENT PROFILE -->
            <section id="patientPage" class="page hidden">

                <div class="page-heading">

                    <div>
                        <p class="section-label">PATIENT MANAGEMENT</p>
                        <h1>Patient Profile</h1>
                        <p class="muted">
                            Manage a fictional patient record for educational use.
                        </p>
                    </div>

                </div>


                <div class="panel patient-panel">

                    <div class="panel-heading">

                        <div>
                            <h2>Patient Details</h2>
                            <p class="muted">
                                Do not enter real patient information.
                            </p>
                        </div>

                        <span class="badge info">
                            Simulated Record
                        </span>

                    </div>


                    <form id="patientForm">

                        <div class="patient-form-grid">

                            <div class="form-group">
                                <label for="patientName">Patient Name</label>

                                <input
                                    type="text"
                                    id="patientName"
                                    placeholder="Enter patient name"
                                >
                            </div>


                            <div class="form-group">
                                <label for="patientId">Patient ID</label>

                                <input
                                    type="text"
                                    id="patientId"
                                    placeholder="Enter patient ID"
                                >
                            </div>


                            <div class="form-group">
                                <label for="patientAge">Age</label>

                                <input
                                    type="number"
                                    id="patientAge"
                                    min="1"
                                    max="120"
                                    placeholder="Enter age"
                                >
                            </div>


                            <div class="form-group">
                                <label for="patientGender">Gender</label>

                                <select id="patientGender">

                                    <option value="">
                                        Select gender
                                    </option>

                                    <option value="Male">Male</option>
                                    <option value="Female">Female</option>
                                    <option value="Other">Other</option>

                                </select>
                            </div>


                            <div class="form-group">
                                <label for="patientCondition">
                                    Medical Condition
                                </label>

                                <input
                                    type="text"
                                    id="patientCondition"
                                    placeholder="Example: Routine monitoring"
                                >
                            </div>


                            <div class="form-group">
                                <label for="patientDoctor">
                                    Doctor Name
                                </label>

                                <input
                                    type="text"
                                    id="patientDoctor"
                                    placeholder="Enter doctor name"
                                >
                            </div>


                            <div class="form-group full-width">
                                <label for="patientNotes">
                                    Additional Notes
                                </label>

                                <textarea
                                    id="patientNotes"
                                    rows="5"
                                    placeholder="Enter additional notes"
                                ></textarea>
                            </div>

                        </div>


                        <div class="form-actions">

                            <button
                                type="submit"
                                id="savePatientButton"
                                class="primary-button"
                            >
                                Save Patient
                            </button>

                            <button
                                type="button"
                                id="clearPatientButton"
                                class="secondary-button"
                            >
                                Clear Details
                            </button>

                        </div>

                        <p id="saveMessage" class="save-message"></p>

                    </form>

                </div>

            </section>


            <!-- TROUBLESHOOTING -->
            <section id="troubleshootingPage" class="page hidden">

                <div class="page-heading">

                    <div>
                        <p class="section-label">TECHNICAL SUPPORT</p>
                        <h1>Troubleshooting Center</h1>
                        <p class="muted">
                            Common ECG monitoring problems and educational solutions.
                        </p>
                    </div>

                </div>


                <div class="troubleshooting-grid">

                    <div class="panel issue-card">
                        <span class="issue-number">01</span>
                        <h2>No ECG Waveform</h2>
                        <p>Check whether ECG monitoring is switched on.</p>
                        <ol>
                            <li>Click Start ECG.</li>
                            <li>Check the ECG status indicator.</li>
                            <li>Confirm that the canvas is visible.</li>
                        </ol>
                    </div>


                    <div class="panel issue-card">
                        <span class="issue-number">02</span>
                        <h2>Noisy Signal</h2>
                        <p>Electrical interference may affect the simulated signal.</p>
                        <ol>
                            <li>Select the Noisy Signal mode.</li>
                            <li>Check the signal description.</li>
                            <li>Return to Normal Sinus Rhythm.</li>
                        </ol>
                    </div>


                    <div class="panel issue-card">
                        <span class="issue-number">03</span>
                        <h2>Lead-Off Warning</h2>
                        <p>The simulated electrodes are not connected.</p>
                        <ol>
                            <li>Select Lead-Off mode.</li>
                            <li>Review the warning message.</li>
                            <li>Select Normal mode to restore the signal.</li>
                        </ol>
                    </div>


                    <div class="panel issue-card">
                        <span class="issue-number">04</span>
                        <h2>Flatline Signal</h2>
                        <p>The simulator is producing no electrical waveform.</p>
                        <ol>
                            <li>Check the selected mode.</li>
                            <li>Confirm ECG is running.</li>
                            <li>Switch back to Normal mode.</li>
                        </ol>
                    </div>


                    <div class="panel issue-card">
                        <span class="issue-number">05</span>
                        <h2>Warning Sound Missing</h2>
                        <p>The browser may block audio until user interaction.</p>
                        <ol>
                            <li>Click Start ECG first.</li>
                            <li>Select a warning mode.</li>
                            <li>Check that the alarm is not muted.</li>
                        </ol>
                    </div>


                    <div class="panel issue-card">
                        <span class="issue-number">06</span>
                        <h2>Patient Details Not Visible</h2>
                        <p>The patient record may not have been saved.</p>
                        <ol>
                            <li>Enter the patient information again.</li>
                            <li>Click Save Patient.</li>
                            <li>Refresh the page and check the form.</li>
                        </ol>
                    </div>

                </div>

            </section>


            <!-- ALARMS -->
            <section id="alarmsPage" class="page hidden">

                <div class="page-heading">

                    <div>
                        <p class="section-label">SAFETY EVENTS</p>
                        <h1>Alarm Center</h1>
                        <p class="muted">
                            Review simulated alarm events.
                        </p>
                    </div>

                </div>


                <div class="panel">

                    <div class="alarm-empty">

                        <div class="alarm-icon">!</div>

                        <h2 id="alarmTitle">No Active Alarms</h2>

                        <p id="alarmDescription">
                            The simulator is currently operating normally.
                        </p>

                    </div>

                </div>

            </section>

        </main>

    </div>


    <script src="script.js"></script>

</body>
</html>
// ==========================================
// ECG GUARDIAN - COMPLETE APPLICATION
// ==========================================


// ---------- ELEMENTS ----------

const loginPage = document.getElementById("loginPage");
const loginForm = document.getElementById("loginForm");
const loginError = document.getElementById("loginError");

const app = document.getElementById("app");
const pages = document.querySelectorAll(".page");
const navItems = document.querySelectorAll("[data-page]");
const pageTitle = document.getElementById("pageTitle");

const logoutButton = document.getElementById("logoutButton");
const darkModeButton = document.getElementById("darkModeButton");

const canvas = document.getElementById("ecgCanvas");
const dashboardCanvas = document.getElementById("dashboardCanvas");

const startEcgButton = document.getElementById("startEcgButton");
const stopEcgButton = document.getElementById("stopEcgButton");
const muteButton = document.getElementById("muteButton");

const waveformMode = document.getElementById("waveformMode");
const modeInformation = document.getElementById("modeInformation");

const ecgStatus = document.getElementById("ecgStatus");
const heartRate = document.getElementById("heartRate");
const dashboardHeartRate = document.getElementById("dashboardHeartRate");
const currentModeLabel = document.getElementById("currentModeLabel");

const savePatientButton = document.getElementById("savePatientButton");
const clearPatientButton = document.getElementById("clearPatientButton");
const patientForm = document.getElementById("patientForm");
const saveMessage = document.getElementById("saveMessage");

const dashboardPatientName = document.getElementById("dashboardPatientName");


// ---------- APPLICATION STATE ----------

let animationId = null;
let isRunning = false;
let animationTime = 0;
let alarmMuted = false;

let audioContext = null;
let warningInterval = null;


// ---------- LOGIN ----------

const correctUserId = "admin";
const correctPassword = "ECG@2026";

function login(event) {
    event.preventDefault();

    const enteredUserId = document.getElementById("email").value.trim();
    const enteredPassword = document.getElementById("password").value.trim();

    if (
        enteredUserId === correctUserId &&
        enteredPassword === correctPassword
    ) {
        sessionStorage.setItem("ecgLoggedIn", "true");

        loginPage.classList.add("hidden");
        app.classList.remove("hidden");

        loginError.textContent = "";

        showPage("dashboardPage");

        console.log("Login successful");
    } else {
        loginError.textContent = "Invalid ID or password.";
    }
}

loginForm.addEventListener("submit", login);


// ---------- PAGE NAVIGATION ----------

function showPage(pageId) {
    const loggedIn = sessionStorage.getItem("ecgLoggedIn");

    if (!loggedIn) {
        loginPage.classList.remove("hidden");
        app.classList.add("hidden");
        return;
    }

    pages.forEach(function (page) {
        page.classList.add("hidden");
    });

    const selectedPage = document.getElementById(pageId);

    if (!selectedPage) {
        return;
    }

    selectedPage.classList.remove("hidden");

    navItems.forEach(function (item) {
        item.classList.remove("active");

        if (item.dataset.page === pageId) {
            item.classList.add("active");
        }
    });

    const pageNames = {
        dashboardPage: "Dashboard",
        monitorPage: "ECG Monitor",
        patientPage: "Patient Profile",
        troubleshootingPage: "Troubleshooting",
        alarmsPage: "Alarm Center"
    };

    pageTitle.textContent = pageNames[pageId] || "ECG Guardian";

    if (pageId === "dashboardPage") {
        resizeDashboardCanvas();
        drawDashboardEcg();
    }

    if (pageId === "monitorPage") {
        resizeCanvas();
        drawEcg();
    }
}

navItems.forEach(function (item) {
    item.addEventListener("click", function () {
        showPage(item.dataset.page);
    });
});


// ---------- LOGOUT ----------

function logout() {
    stopEcg();

    sessionStorage.removeItem("ecgLoggedIn");

    app.classList.add("hidden");
    loginPage.classList.remove("hidden");

    document.getElementById("email").value = "";
    document.getElementById("password").value = "";

    showPage("dashboardPage");
}

logoutButton.addEventListener("click", logout);


// ---------- DARK MODE ----------

darkModeButton.addEventListener("click", function () {
    document.body.classList.toggle("dark-mode");

    const darkModeEnabled = document.body.classList.contains("dark-mode");

    localStorage.setItem("ecgDarkMode", darkModeEnabled ? "on" : "off");
});

if (localStorage.getItem("ecgDarkMode") === "on") {
    document.body.classList.add("dark-mode");
}


// ---------- CANVAS ----------

function resizeCanvas() {
    const container = canvas.parentElement;

    canvas.width = Math.max(container.clientWidth - 56, 300);
    canvas.height = 320;
}

function resizeDashboardCanvas() {
    const container = dashboardCanvas.parentElement;

    dashboardCanvas.width = Math.max(container.clientWidth - 56, 300);
    dashboardCanvas.height = 230;
}

function drawGrid(ctx, width, height) {
    ctx.fillStyle = "#071b24";
    ctx.fillRect(0, 0, width, height);

    ctx.strokeStyle = "rgba(45, 190, 160, 0.16)";
    ctx.lineWidth = 1;

    for (let x = 0; x < width; x += 20) {
        ctx.beginPath();
        ctx.moveTo(x, 0);
        ctx.lineTo(x, height);
        ctx.stroke();
    }

    for (let y = 0; y < height; y += 20) {
        ctx.beginPath();
        ctx.moveTo(0, y);
        ctx.lineTo(width, y);
        ctx.stroke();
    }
}


// ---------- ECG WAVEFORM ----------

function getWaveformValue(time, mode) {
    if (mode === "leadoff" || mode === "flatline") {
        return 0;
    }

    let cycleLength = 180;

    if (mode === "tachycardia") {
        cycleLength = 115;
    }

    if (mode === "bradycardia") {
        cycleLength = 260;
    }

    if (mode === "irregular") {
        cycleLength = 150 + Math.sin(time / 80) * 45;
    }

    const position = time % cycleLength;

    let value = 0;

    if (position < 35) {
        value = 0;
    } else if (position < 50) {
        value = -8 * Math.sin((position - 35) * Math.PI / 15);
    } else if (position < 58) {
        value = 0;
    } else if (position < 64) {
        value = 12;
    } else if (position < 70) {
        value = -75;
    } else if (position < 76) {
        value = 28;
    } else if (position < 100) {
        value = 0;
    } else if (position < 125) {
        value = -15 * Math.sin((position - 100) * Math.PI / 25);
    }

    if (mode === "noisy") {
        value += (Math.random() - 0.5) * 35;
    }

    return value;
}

function drawEcg() {
    const ctx = canvas.getContext("2d");

    const width = canvas.width;
    const height = canvas.height;

    drawGrid(ctx, width, height);

    const mode = waveformMode.value;
    const centerY = height / 2;

    ctx.beginPath();
    ctx.strokeStyle = "#35e0a1";
    ctx.lineWidth = 2.5;

    for (let x = 0; x < width; x++) {
        const time = x + animationTime;
        const value = getWaveformValue(time, mode);
        const y = centerY + value;

        if (x === 0) {
            ctx.moveTo(x, y);
        } else {
            ctx.lineTo(x, y);
        }
    }

    ctx.stroke();

    if (isRunning) {
        animationTime += 2;
        animationId = requestAnimationFrame(drawEcg);
    }
}

function drawDashboardEcg() {
    const ctx = dashboardCanvas.getContext("2d");

    const width = dashboardCanvas.width;
    const height = dashboardCanvas.height;

    drawGrid(ctx, width, height);

    const centerY = height / 2;

    ctx.beginPath();
    ctx.strokeStyle = "#35e0a1";
    ctx.lineWidth = 2;

    for (let x = 0; x < width; x++) {
        const value = getWaveformValue(x + animationTime, "normal");
        const y = centerY + value;

        if (x === 0) {
            ctx.moveTo(x, y);
        } else {
            ctx.lineTo(x, y);
        }
    }

    ctx.stroke();
}


// ---------- ECG CONTROLS ----------

function startEcg() {
    if (isRunning) {
        return;
    }

    isRunning = true;

    ecgStatus.textContent = "● ECG ON";
    ecgStatus.className = "badge success";

    drawEcg();
}

function stopEcg() {
    isRunning = false;

    cancelAnimationFrame(animationId);
    stopWarningSound();

    ecgStatus.textContent = "● ECG OFF";
    ecgStatus.className = "badge danger";

    drawEcg();
}

startEcgButton.addEventListener("click", startEcg);
stopEcgButton.addEventListener("click", stopEcg);


// ---------- ECG MODES ----------

function updateModeInformation() {
    const mode = waveformMode.value;

    const information = {
        normal: "Normal simulated sinus rhythm.",
        tachycardia: "Simulated fast heart rate.",
        bradycardia: "Simulated slow heart rate.",
        irregular: "Simulated irregular rhythm.",
        noisy: "Electrical interference detected in the simulated signal.",
        leadoff: "Simulated electrode connection problem.",
        flatline: "No simulated ECG signal detected."
    };

    const rates = {
        normal: 72,
        tachycardia: 125,
        bradycardia: 48,
        irregular: 88,
        noisy: 72,
        leadoff: 0,
        flatline: 0
    };

    const labels = {
        normal: "Normal Sinus Rhythm",
        tachycardia: "Tachycardia",
        bradycardia: "Bradycardia",
        irregular: "Irregular Rhythm",
        noisy: "Noisy Signal",
        leadoff: "Lead-Off",
        flatline: "Flatline"
    };

    modeInformation.textContent = information[mode];
    currentModeLabel.textContent = labels[mode];

    heartRate.innerHTML = `${rates[mode]} <small>BPM</small>`;
    dashboardHeartRate.textContent = `${rates[mode]} BPM`;

    if (
        mode === "noisy" ||
        mode === "leadoff" ||
        mode === "flatline"
    ) {
        document.getElementById("alarmTitle").textContent =
            "Active Simulated Alarm";

        document.getElementById("alarmDescription").textContent =
            information[mode];

        if (!alarmMuted) {
            startWarningSound();
        }
    } else {
        document.getElementById("alarmTitle").textContent =
            "No Active Alarms";

        document.getElementById("alarmDescription").textContent =
            "The simulator is currently operating normally.";

        stopWarningSound();
    }

    drawEcg();
}

waveformMode.addEventListener("change", updateModeInformation);


// ---------- WARNING SOUND ----------

function playWarningSound() {
    if (alarmMuted) {
        return;
    }

    if (!audioContext) {
        audioContext = new (
            window.AudioContext ||
            window.webkitAudioContext
        )();
    }

    const oscillator = audioContext.createOscillator();
    const gainNode = audioContext.createGain();

    oscillator.type = "square";
    oscillator.frequency.value = 850;

    gainNode.gain.value = 0.08;

    oscillator.connect(gainNode);
    gainNode.connect(audioContext.destination);

    oscillator.start();

    setTimeout(function () {
        oscillator.stop();
    }, 180);
}

function startWarningSound() {
    stopWarningSound();

    if (alarmMuted) {
        return;
    }

    playWarningSound();

    warningInterval = setInterval(function () {
        playWarningSound();
    }, 900);
}

function stopWarningSound() {
    if (warningInterval) {
        clearInterval(warningInterval);
        warningInterval = null;
    }
}

muteButton.addEventListener("click", function () {
    alarmMuted = !alarmMuted;

    if (alarmMuted) {
        muteButton.textContent = "Unmute Alarm";
        stopWarningSound();
    } else {
        muteButton.textContent = "Mute Alarm";
        updateModeInformation();
    }
});


// ---------- PATIENT PROFILE ----------

function getPatientDetails() {
    return {
        name: document.getElementById("patientName").value.trim(),
        id: document.getElementById("patientId").value.trim(),
        age: document.getElementById("patientAge").value.trim(),
        gender: document.getElementById("patientGender").value,
        condition: document.getElementById("patientCondition").value.trim(),
        doctor: document.getElementById("patientDoctor").value.trim(),
        notes: document.getElementById("patientNotes").value.trim()
    };
}

function savePatientDetails(event) {
    event.preventDefault();

    const patientDetails = getPatientDetails();

    localStorage.setItem(
        "ecgGuardianPatient",
        JSON.stringify(patientDetails)
    );

    saveMessage.textContent = "✓ Patient details saved successfully.";

    dashboardPatientName.textContent =
        patientDetails.name || "Not Added";
}

function loadPatientDetails() {
    const savedPatient = localStorage.getItem("ecgGuardianPatient");

    if (!savedPatient) {
        return;
    }

    const patientDetails = JSON.parse(savedPatient);

    document.getElementById("patientName").value =
        patientDetails.name || "";

    document.getElementById("patientId").value =
        patientDetails.id || "";

    document.getElementById("patientAge").value =
        patientDetails.age || "";

    document.getElementById("patientGender").value =
        patientDetails.gender || "";

    document.getElementById("patientCondition").value =
        patientDetails.condition || "";

    document.getElementById("patientDoctor").value =
        patientDetails.doctor || "";

    document.getElementById("patientNotes").value =
        patientDetails.notes || "";

    dashboardPatientName.textContent =
        patientDetails.name || "Not Added";
}

function clearPatientDetails() {
    patientForm.reset();

    localStorage.removeItem("ecgGuardianPatient");

    saveMessage.textContent = "Patient details cleared.";

    dashboardPatientName.textContent = "Not Added";
}

patientForm.addEventListener("submit", savePatientDetails);
clearPatientButton.addEventListener("click", clearPatientDetails);

loadPatientDetails();


// ---------- RESIZE ----------

window.addEventListener("resize", function () {
    if (!app.classList.contains("hidden")) {
        resizeDashboardCanvas();
        drawDashboardEcg();

        if (!document.getElementById("monitorPage").classList.contains("hidden")) {
            resizeCanvas();
            drawEcg();
        }
    }
});


// ---------- INITIAL STATE ----------

if (sessionStorage.getItem("ecgLoggedIn") === "true") {
    loginPage.classList.add("hidden");
    app.classList.remove("hidden");
    showPage("dashboardPage");
} else {
    loginPage.classList.remove("hidden");
    app.classList.add("hidden");
}[script.js](https://github.com/user-attachments/files/35158787/script.js)


[style.css](https://github.com/user-attachments/files/35158773/style.css)* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

:root {
    --background: #f1f5f9;
    --card: #ffffff;
    --text: #0f172a;
    --muted: #64748b;
    --border: #e2e8f0;
    --primary: #0f766e;
    --primary-light: #14b8a6;
    --danger: #dc2626;
    --sidebar: #071b24;
}

body {
    min-height: 100vh;
    font-family: Arial, Helvetica, sans-serif;
    background: var(--background);
    color: var(--text);
}

button,
input,
select,
textarea {
    font: inherit;
}

button {
    cursor: pointer;
}

.hidden {
    display: none !important;
}


/* LOGIN */

.login-page {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 24px;
    background:
        radial-gradient(circle at top right, #d1fae5, transparent 35%),
        #f1f5f9;
}

.login-card {
    width: 100%;
    max-width: 440px;
    padding: 42px;
    background: #ffffff;
    border: 1px solid var(--border);
    border-radius: 24px;
    box-shadow: 0 20px 60px rgba(15, 23, 42, 0.12);
    text-align: center;
}

.brand-logo,
.small-logo {
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    background: linear-gradient(135deg, #0f766e, #14b8a6);
    border-radius: 14px;
    font-size: 30px;
    font-weight: bold;
}

.brand-logo {
    width: 68px;
    height: 68px;
    margin: 0 auto 20px;
}

.company-name {
    color: var(--primary);
    font-size: 12px;
    font-weight: bold;
    letter-spacing: 1.5px;
    text-transform: uppercase;
}

.login-card h1 {
    margin: 10px 0;
    font-size: 32px;
}

.login-description {
    color: var(--muted);
    line-height: 1.6;
    margin-bottom: 30px;
}

.login-card form {
    text-align: left;
}

label {
    display: block;
    margin-bottom: 8px;
    color: #334155;
    font-size: 13px;
    font-weight: bold;
}

input,
select,
textarea {
    width: 100%;
    padding: 14px;
    margin-bottom: 18px;
    border: 1px solid #cbd5e1;
    border-radius: 10px;
    background: #f8fafc;
    color: var(--text);
    outline: none;
}

input:focus,
select:focus,
textarea:focus {
    border-color: var(--primary);
    background: white;
    box-shadow: 0 0 0 3px rgba(15, 118, 110, 0.12);
}

.primary-button,
.secondary-button {
    border-radius: 10px;
    padding: 13px 20px;
    font-weight: bold;
    transition: 0.2s ease;
}

.primary-button {
    border: none;
    color: white;
    background: linear-gradient(135deg, #0f766e, #14b8a6);
    box-shadow: 0 6px 15px rgba(15, 118, 110, 0.2);
}

.primary-button:hover {
    transform: translateY(-2px);
}

.secondary-button {
    border: 1px solid #cbd5e1;
    background: white;
    color: #334155;
}

.secondary-button:hover {
    background: #f1f5f9;
}

.login-card .primary-button {
    width: 100%;
    margin-top: 8px;
}

.login-error {
    min-height: 20px;
    margin-top: 12px;
    color: #dc2626;
    font-size: 13px;
    text-align: center;
}

.login-note {
    margin-top: 25px;
    color: var(--muted);
    font-size: 12px;
}


/* APPLICATION LAYOUT */

.app {
    min-height: 100vh;
    display: flex;
}

.sidebar {
    width: 270px;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    padding: 25px 18px;
    background: var(--sidebar);
    color: white;
}

.sidebar-brand {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 0 10px 30px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.small-logo {
    width: 42px;
    height: 42px;
    font-size: 22px;
    flex-shrink: 0;
}

.sidebar-brand h2 {
    font-size: 17px;
}

.sidebar-brand p {
    margin-top: 4px;
    color: #94a3b8;
    font-size: 11px;
}

.navigation {
    display: flex;
    flex-direction: column;
    gap: 8px;
    margin-top: 28px;
}

.nav-item,
.sidebar-action {
    width: 100%;
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 14px;
    border: none;
    border-radius: 10px;
    background: transparent;
    color: #cbd5e1;
    text-align: left;
}

.nav-item:hover,
.nav-item.active {
    background: rgba(20, 184, 166, 0.16);
    color: white;
}

.nav-item span {
    width: 22px;
    color: #5eead4;
    font-size: 18px;
    text-align: center;
}

.sidebar-bottom {
    margin-top: auto;
}

.sidebar-action:hover {
    background: rgba(255, 255, 255, 0.08);
    color: white;
}

.logout-button {
    color: #fca5a5;
}

.main-content {
    flex: 1;
    min-width: 0;
    padding: 30px;
}

.topbar {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    margin-bottom: 35px;
}

.topbar-label,
.section-label {
    color: var(--primary);
    font-size: 11px;
    font-weight: bold;
    letter-spacing: 1.5px;
}

.topbar h2 {
    margin-top: 8px;
}

.online-status {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 10px 14px;
    border: 1px solid #bbf7d0;
    border-radius: 999px;
    background: #f0fdf4;
    color: #166534;
    font-size: 13px;
    font-weight: bold;
}

.online-status span {
    width: 8px;
    height: 8px;
    border-radius: 50%;
    background: #22c55e;
}


/* COMMON */

.page {
    max-width: 1300px;
    margin: 0 auto;
}

.welcome-section,
.page-heading {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 20px;
    margin-bottom: 30px;
}

h1 {
    margin-top: 8px;
    font-size: 30px;
}

h2 {
    font-size: 21px;
}

.muted {
    margin-top: 8px;
    color: var(--muted);
    line-height: 1.6;
}

.panel {
    padding: 28px;
    border: 1px solid var(--border);
    border-radius: 18px;
    background: var(--card);
    box-shadow: 0 10px 25px rgba(15, 23, 42, 0.05);
}

.panel-heading {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 20px;
    margin-bottom: 24px;
}

.badge {
    display: inline-flex;
    align-items: center;
    padding: 8px 12px;
    border-radius: 999px;
    font-size: 12px;
    font-weight: bold;
    white-space: nowrap;
}

.badge.success {
    background: #dcfce7;
    color: #166534;
}

.badge.danger {
    background: #fee2e2;
    color: #991b1b;
}

.badge.info {
    background: #dbeafe;
    color: #1d4ed8;
}


/* DASHBOARD */

.stat-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    margin-bottom: 24px;
}

.stat-card {
    padding: 24px;
    border: 1px solid var(--border);
    border-radius: 16px;
    background: var(--card);
}

.stat-card p {
    color: var(--muted);
    font-size: 13px;
}

.stat-card h2 {
    margin: 12px 0;
}

.stat-green {
    color: #15803d;
    font-size: 12px;
    font-weight: bold;
}

.stat-muted {
    color: var(--muted);
    font-size: 12px;
}

.dashboard-grid {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 24px;
}

#dashboardCanvas {
    width: 100%;
    height: 230px;
    display: block;
    margin-bottom: 20px;
    border-radius: 12px;
    background: #071b24;
}

.quick-actions {
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.quick-actions button {
    padding: 16px;
    border: 1px solid var(--border);
    border-radius: 10px;
    background: #f8fafc;
    color: var(--text);
    text-align: left;
    font-weight: bold;
}

.quick-actions button:hover {
    border-color: var(--primary);
    color: var(--primary);
}


/* MONITOR */

.monitor-topbar {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    margin-bottom: 25px;
}

.monitor-topbar h2 {
    margin-top: 8px;
    font-size: 30px;
}

.monitor-topbar h2 small {
    font-size: 13px;
    color: var(--muted);
}

.monitor-topbar h3 {
    margin-top: 8px;
    font-size: 16px;
}

#ecgCanvas {
    width: 100%;
    height: 320px;
    display: block;
    border-radius: 12px;
    background: #071b24;
}

.monitor-controls {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 22px;
}

.mode-area {
    max-width: 500px;
    margin-top: 25px;
}

.mode-area select {
    margin-bottom: 8px;
}

.mode-information {
    color: var(--muted);
    font-size: 13px;
    line-height: 1.6;
}


/* PATIENT */

.patient-panel {
    max-width: 1100px;
}

.patient-form-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 22px;
}

.form-group {
    display: flex;
    flex-direction: column;
}

.form-group input,
.form-group select,
.form-group textarea {
    margin-bottom: 0;
}

.full-width {
    grid-column: 1 / -1;
}

.form-actions {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 28px;
    padding-top: 24px;
    border-top: 1px solid var(--border);
}

.save-message {
    min-height: 20px;
    margin-top: 18px;
    color: #15803d;
    font-size: 13px;
    font-weight: bold;
}


/* TROUBLESHOOTING */

.troubleshooting-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 22px;
}

.issue-card {
    position: relative;
}

.issue-number {
    display: inline-flex;
    margin-bottom: 18px;
    color: var(--primary);
    font-size: 13px;
    font-weight: bold;
}

.issue-card h2 {
    margin-bottom: 12px;
}

.issue-card p {
    color: var(--muted);
    line-height: 1.6;
}

.issue-card ol {
    margin-top: 18px;
    padding-left: 20px;
    color: var(--muted);
    line-height: 1.9;
    font-size: 13px;
}


/* ALARMS */

.alarm-empty {
    padding: 50px 20px;
    text-align: center;
}

.alarm-icon {
    width: 60px;
    height: 60px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 0 auto 20px;
    border-radius: 50%;
    background: #dcfce7;
    color: #166534;
    font-size: 30px;
    font-weight: bold;
}

.alarm-empty p {
    margin-top: 12px;
    color: var(--muted);
}


/* DARK MODE */

body.dark-mode {
    --background: #0f172a;
    --card: #1e293b;
    --text: #e2e8f0;
    --muted: #94a3b8;
    --border: #334155;
}

body.dark-mode input,
body.dark-mode select,
body.dark-mode textarea,
body.dark-mode .quick-actions button,
body.dark-mode .secondary-button {
    background: #0f172a;
    color: #e2e8f0;
    border-color: #475569;
}

body.dark-mode .login-page {
    background: #0f172a;
}

body.dark-mode .login-card {
    background: #1e293b;
    border-color: #334155;
}

body.dark-mode label {
    color: #cbd5e1;
}


/* RESPONSIVE */

@media (max-width: 1000px) {
    .sidebar {
        width: 220px;
    }

    .dashboard-grid,
    .troubleshooting-grid {
        grid-template-columns: 1fr;
    }

    .stat-grid {
        grid-template-columns: 1fr;
    }
}

@media (max-width: 750px) {
    .app {
        display: block;
    }

    .sidebar {
        width: 100%;
        min-height: auto;
    }

    .navigation {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
    }

    .sidebar-bottom {
        margin-top: 20px;
    }

    .main-content {
        padding: 20px;
    }

    .welcome-section,
    .page-heading,
    .topbar {
        flex-direction: column;
    }

    .patient-form-grid,
    .monitor-topbar {
        grid-template-columns: 1fr;
    }

    .full-width {
        grid-column: auto;
    }

    .panel {
        padding: 20px;
    }
}
# ECG-Guardian
