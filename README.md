<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>PMIS | Project Narrative Management System</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #f0f6f2;
            font-family: 'Inter', sans-serif;
            color: #1a3a2e;
            padding: 20px;
        }

        .app-container {
            max-width: 1400px;
            margin: 0 auto;
        }

        .main-header {
            background: linear-gradient(115deg, #0b3326 0%, #1b5e45 100%);
            border-radius: 24px;
            padding: 24px 28px;
            margin-bottom: 24px;
            color: white;
            box-shadow: 0 12px 28px -10px rgba(0,0,0,0.2);
        }

        .brand h1 {
            font-size: 1.7rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .brand i {
            background: #ffcd6b;
            color: #1a4d34;
            border-radius: 50px;
            padding: 10px;
            font-size: 1.2rem;
        }

        .sub {
            color: #c7f0e2;
            margin-top: 6px;
            font-size: 0.85rem;
        }

        .nav-pills {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 22px;
            border-bottom: 1px solid rgba(255,255,255,0.2);
            padding-bottom: 8px;
        }

        .nav-btn {
            background: transparent;
            border: none;
            font-weight: 600;
            padding: 8px 22px;
            border-radius: 40px;
            font-size: 0.85rem;
            cursor: pointer;
            color: #f0faf5;
            font-family: 'Inter', sans-serif;
            transition: 0.2s;
        }

        .nav-btn i {
            margin-right: 8px;
        }

        .nav-btn.active {
            background: #ffcd6b;
            color: #1b422f;
        }

        .nav-btn:hover:not(.active) {
            background: rgba(255,255,255,0.15);
        }

        .panel {
            display: none;
            animation: fadeIn 0.25s ease;
        }

        .panel.active-panel {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(6px);}
            to { opacity: 1; transform: translateY(0);}
        }

        .card {
            background: white;
            border-radius: 24px;
            padding: 24px;
            margin-bottom: 24px;
            box-shadow: 0 4px 16px rgba(0,0,0,0.04);
        }

        .form-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
            margin-bottom: 24px;
        }

        .input-group {
            display: flex;
            flex-direction: column;
            gap: 6px;
        }

        .input-group label {
            font-weight: 700;
            font-size: 0.7rem;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            color: #548b74;
        }

        input, select, textarea {
            padding: 10px 14px;
            border-radius: 16px;
            border: 1.5px solid #e0ede5;
            font-family: 'Inter', sans-serif;
            font-size: 0.85rem;
            background: white;
        }

        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: #ffcd6b;
            box-shadow: 0 0 0 3px rgba(255,205,107,0.2);
        }

        button {
            background: #1e5e48;
            border: none;
            padding: 10px 24px;
            border-radius: 40px;
            font-weight: 600;
            color: white;
            cursor: pointer;
            font-family: 'Inter', sans-serif;
            font-size: 0.8rem;
        }

        button i {
            margin-right: 8px;
        }

        button.btn-outline {
            background: white;
            border: 1.5px solid #caddd4;
            color: #1e5e48;
        }

        button.btn-outline:hover {
            background: #f5faf7;
        }

        button:hover {
            background: #0f4635;
            transform: translateY(-1px);
        }

        table {
            width: 100%;
            border-collapse: collapse;
            font-size: 0.8rem;
        }

        th {
            text-align: left;
            padding: 12px 10px;
            background: #f9fefb;
            border-bottom: 2px solid #e2efe8;
            font-weight: 700;
        }

        td {
            padding: 12px 10px;
            border-bottom: 1px solid #eaf3ee;
            vertical-align: top;
        }

        .badge {
            background: #eafaf2;
            padding: 4px 12px;
            border-radius: 30px;
            font-size: 0.65rem;
            font-weight: 700;
            display: inline-block;
        }

        .action-icon {
            cursor: pointer;
            margin: 0 6px;
            color: #8bb3a2;
        }

        .action-icon:hover {
            color: #c23b22;
        }

        .stats-row {
            display: flex;
            flex-wrap: wrap;
            gap: 16px;
            margin-bottom: 24px;
        }

        .stat-card {
            background: white;
            flex: 1;
            min-width: 160px;
            border-radius: 20px;
            padding: 16px;
            border-left: 4px solid #ffcd6b;
            box-shadow: 0 2px 8px rgba(0,0,0,0.03);
        }

        .stat-number {
            font-size: 1.8rem;
            font-weight: 800;
            color: #1e5e48;
            margin-top: 6px;
        }

        hr {
            margin: 16px 0;
            border-color: #e2ede6;
        }

        .narrative-card {
            background: #fefef7;
            border-radius: 20px;
            padding: 16px;
            margin-bottom: 12px;
            cursor: pointer;
            border: 1px solid #e2ede5;
            transition: all 0.2s;
        }

        .narrative-card:hover {
            background: #fcf9ef;
            border-color: #ffcd6b;
        }

        @media (max-width: 680px) {
            .form-grid { grid-template-columns: 1fr; }
            th, td { font-size: 0.7rem; padding: 8px 6px; }
            .brand h1 { font-size: 1.3rem; }
        }
    </style>
</head>
<body>
<div class="app-container">
    <div class="main-header">
        <div class="brand">
            <h1><i class="fas fa-chalkboard-user"></i> PMIS · Project Narrative Manager</h1>
            <div class="sub">Register projects · Track narratives · TaRL literacy framework ready for your data</div>
        </div>
        <div class="nav-pills">
            <button class="nav-btn active" data-panel="registerPanel"><i class="fas fa-folder-plus"></i> New Project</button>
            <button class="nav-btn" data-panel="listPanel"><i class="fas fa-list-check"></i> Project Portfolio</button>
            <button class="nav-btn" data-panel="narrativePanel"><i class="fas fa-book-open"></i> Narratives & Reports</button>
        </div>
    </div>

    <!-- REGISTER PROJECT PANEL -->
    <div id="registerPanel" class="panel active-panel">
        <div class="card">
            <h2><i class="fas fa-pen-ruler"></i> Register New Project</h2>
            <p style="margin-bottom: 20px; color: #4f7767;">Fill in project details — all fields are ready for your data.</p>
            <div class="form-grid">
                <div class="input-group"><label>Project Title *</label><input type="text" id="projName" placeholder="e.g., TaRL Teacher Training - Afar"></div>
                <div class="input-group"><label>Region / Location</label><input type="text" id="projRegion" placeholder="Afar, Oromia, National"></div>
                <div class="input-group"><label>Budget (USD) - optional</label><input type="text" id="projBudget" placeholder="Enter amount or leave empty"></div>
                <div class="input-group"><label>Activity Code</label><input type="text" id="projCode" placeholder="e.g., 4.5.2, 4.7.1"></div>
                <div class="input-group"><label>Start Date</label><input type="date" id="projStart"></div>
                <div class="input-group"><label>End Date</label><input type="date" id="projEnd"></div>
                <div class="input-group"><label>Status</label>
                    <select id="projStatus">
                        <option value="Planning">Planning</option>
                        <option value="In Progress">In Progress</option>
                        <option value="Completed">Completed</option>
                        <option value="On Hold">On Hold</option>
                    </select>
                </div>
                <div class="input-group"><label>Key Partners / Stakeholders</label><input type="text" id="projPartners" placeholder="REB, WEO, Imagine1day"></div>
            </div>
            <div class="input-group" style="margin-bottom: 20px;"><label>Project Narrative / Description</label>
                <textarea id="projDesc" rows="4" placeholder="Describe the project: objectives, TaRL activities, target groups, implementation approach..."></textarea>
            </div>
            <div class="input-group" style="margin-bottom: 24px;"><label>Key Achievements / Milestones</label>
                <textarea id="projAchievements" rows="3" placeholder="e.g., baseline completed, teachers trained, reading clubs established..."></textarea>
            </div>
            <div style="display: flex; gap: 16px; justify-content: flex-end;">
                <button id="registerProjBtn"><i class="fas fa-save"></i> Register Project</button>
                <button id="clearFormBtn" class="btn-outline"><i class="fas fa-eraser"></i> Clear Form</button>
            </div>
        </div>
        <div class="card">
            <h3><i class="fas fa-graduation-cap"></i> TaRL Guidelines for Narrative Building</h3>
            <ul style="margin-left: 20px; margin-top: 12px; color: #2b5f49; line-height: 1.6;">
                <li><strong>Core skills:</strong> Listening, observing, speaking, reading (Letter to Word to Paragraph to Story), writing.</li>
                <li><strong>Level-specific activities:</strong> Syllable chart, picture reading, mind map, basket game, "What Next?" story making.</li>
                <li><strong>Grouping:</strong> Homogeneous or heterogeneous (Beginner/Letter, Word/Paragraph, Story).</li>
                <li><strong>Assessment:</strong> Baseline/midline/endline one-to-one oral reading tests.</li>
            </ul>
        </div>
    </div>

    <!-- PROJECT PORTFOLIO -->
    <div id="listPanel" class="panel">
        <div class="card">
            <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap;">
                <h2><i class="fas fa-diagram-project"></i> Project Portfolio</h2>
                <button id="exportCsvBtn" class="btn-outline"><i class="fas fa-file-csv"></i> Export to CSV</button>
            </div>
            <div style="overflow-x: auto; margin-top: 20px;">
                <table id="projectTable">
                    <thead>
                        <tr><th>Code</th><th>Project Name</th><th>Region</th><th>Budget</th><th>Timeline</th><th>Status</th><th>Actions</th>
                    </thead>
                    <tbody id="projectListBody">
                        <tr><td colspan="7" style="text-align:center;">No projects yet — start by registering a project.</td></tr>
                    </tbody>
                </table>
            </div>
        </div>
    </div>

    <!-- NARRATIVES & REPORTING -->
    <div id="narrativePanel" class="panel">
        <div class="stats-row">
            <div class="stat-card"><i class="fas fa-folder-open"></i> <strong>Total Projects</strong><div class="stat-number" id="totalProjectsStat">0</div></div>
            <div class="stat-card"><i class="fas fa-play-circle"></i> <strong>Active Projects</strong><div class="stat-number" id="activeProjectsStat">0</div></div>
            <div class="stat-card"><i class="fas fa-flag-checkered"></i> <strong>Completed</strong><div class="stat-number" id="completedProjectsStat">0</div></div>
        </div>
        
        <div class="card">
            <h2><i class="fas fa-book-open"></i> Project Narratives & Progress Stories</h2>
            <p style="margin-bottom: 16px;">Click on any project to view or edit its full narrative, achievements, and implementation details.</p>
            <div id="narrativeListContainer" style="max-height: 420px; overflow-y: auto;">
            </div>
        </div>

        <div class="card" id="narrativeDetailCard" style="display: none;">
            <div style="display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap;">
                <h3 id="narrativeTitle">Project Narrative</h3>
                <button id="closeNarrativeBtn" class="btn-outline"><i class="fas fa-times"></i> Close</button>
            </div>
            <div id="narrativeDetailContent" style="margin-top: 16px; line-height: 1.6;"></div>
            <hr>
            <div style="display: flex; gap: 12px; justify-content: flex-end;">
                <button id="editNarrativeBtn"><i class="fas fa-edit"></i> Edit Narrative</button>
            </div>
            <div id="editNarrativeArea" style="display: none; margin-top: 16px;">
                <label style="font-weight:600;">Description / Methodology:</label>
                <textarea id="editDescText" rows="4" style="width:100%; margin-bottom: 12px; border-radius:16px; border:1px solid #ddd; padding:10px;"></textarea>
                <label style="font-weight:600;">Key Achievements:</label>
                <textarea id="editAchieveText" rows="3" style="width:100%; margin-bottom: 12px; border-radius:16px; border:1px solid #ddd; padding:10px;"></textarea>
                <button id="saveNarrativeEditBtn"><i class="fas fa-save"></i> Save Changes</button>
                <button id="cancelEditBtn" class="btn-outline">Cancel</button>
            </div>
        </div>
    </div>
</div>

<script>
    (function() {
        let projects = [];

        function loadProjects() {
            var stored = localStorage.getItem("pmis_narrative_projects_v2");
            if(stored) {
                projects = JSON.parse(stored);
            } else {
                projects = [];
            }
            renderAll();
        }

        function saveProjects() {
            localStorage.setItem("pmis_narrative_projects_v2", JSON.stringify(projects));
        }

        function addProject(project) {
            project.id = Date.now();
            projects.push(project);
            saveProjects();
            renderAll();
        }

        function deleteProject(id) {
            if(confirm("Delete this project? The narrative will be lost.")) {
                projects = projects.filter(function(p) { return p.id !== id; });
                saveProjects();
                renderAll();
                var detailCard = document.getElementById("narrativeDetailCard");
                if(detailCard) detailCard.style.display = "none";
                currentNarrativeProjectId = null;
            }
        }

        function updateProject(id, updatedFields) {
            for(var i = 0; i < projects.length; i++) {
                if(projects[i].id === id) {
                    for(var key in updatedFields) {
                        if(updatedFields.hasOwnProperty(key)) {
                            projects[i][key] = updatedFields[key];
                        }
                    }
                    break;
                }
            }
            saveProjects();
            renderAll();
        }

        function renderAll() {
            renderProjectList();
            renderNarrativeList();
            updateStats();
        }

        function renderProjectList() {
            var tbody = document.getElementById("projectListBody");
            if(!tbody) return;
            if(projects.length === 0) {
                tbody.innerHTML = '<tr><td colspan="7" style="text-align:center;">No projects yet — start by registering a project.</td></tr>';
                return;
            }
            tbody.innerHTML = "";
            for(var i = 0; i < projects.length; i++) {
                var p = projects[i];
                var budgetDisplay = p.budget ? "$" + p.budget : "—";
                var descShort = (p.desc || "").substring(0,55);
                var row = document.createElement('tr');
                row.innerHTML = '<td>' + escapeHtml(p.code || "—") + '</td>' +
                    '<td><strong>' + escapeHtml(p.name) + '</strong><br><small>' + escapeHtml(descShort) + '</small></td>' +
                    '<td>' + escapeHtml(p.region || "—") + '</td>' +
                    '<td>' + budgetDisplay + '</td>' +
                    '<td>' + (p.start || "—") + ' → ' + (p.end || "—") + '</td>' +
                    '<td><span class="badge">' + (p.status || "Planning") + '</span></td>' +
                    '<td><i class="fas fa-trash-alt action-icon" data-id="' + p.id + '" title="Delete"></i></td>';
                tbody.appendChild(row);
            }
            var deleteIcons = document.querySelectorAll('.fa-trash-alt');
            for(var j = 0; j < deleteIcons.length; j++) {
                deleteIcons[j].addEventListener('click', function(e) {
                    var id = parseInt(this.getAttribute('data-id'));
                    deleteProject(id);
                });
            }
        }

        function renderNarrativeList() {
            var container = document.getElementById("narrativeListContainer");
            if(!container) return;
            if(projects.length === 0) {
                container.innerHTML = '<div style="padding: 32px; text-align:center; background:#fafefa; border-radius:20px;">✨ No projects yet. Register a project to build narratives.</div>';
                return;
            }
            container.innerHTML = "";
            for(var i = 0; i < projects.length; i++) {
                var p = projects[i];
                var descPreview = p.desc ? (p.desc.substring(0,100) + (p.desc.length > 100 ? "…" : "")) : "No narrative description added yet.";
                var cardDiv = document.createElement('div');
                cardDiv.className = "narrative-card";
                cardDiv.setAttribute('data-id', p.id);
                cardDiv.innerHTML = '<div style="display:flex; justify-content:space-between; align-items:center;">' +
                    '<div><i class="fas fa-file-alt" style="color:#1e5e48;"></i> <strong>' + escapeHtml(p.name) + '</strong> ' +
                    '<span style="font-size:0.65rem; background:#eef3ef; padding:2px 10px; border-radius:20px; margin-left:8px;">' + (p.status || "Planning") + '</span></div>' +
                    '<i class="fas fa-chevron-right" style="color:#8bb3a2;"></i></div>' +
                    '<div style="font-size:0.7rem; color:#5f8b79; margin-top:6px;">' + (p.region ? p.region : "No region") + ' | Code: ' + (p.code || "—") + '</div>' +
                    '<div style="margin-top:8px; font-size:0.8rem; color:#2d5a48;">' + escapeHtml(descPreview) + '</div>';
                cardDiv.addEventListener('click', (function(projectId) {
                    return function() { showNarrativeDetail(projectId); };
                })(p.id));
                container.appendChild(cardDiv);
            }
        }

        var currentNarrativeProjectId = null;

        function showNarrativeDetail(projectId) {
            var project = null;
            for(var i = 0; i < projects.length; i++) {
                if(projects[i].id === projectId) {
                    project = projects[i];
                    break;
                }
            }
            if(!project) return;
            currentNarrativeProjectId = project.id;
            var detailCard = document.getElementById("narrativeDetailCard");
            var titleEl = document.getElementById("narrativeTitle");
            var contentDiv = document.getElementById("narrativeDetailContent");
            var editArea = document.getElementById("editNarrativeArea");
            var editDesc = document.getElementById("editDescText");
            var editAchieve = document.getElementById("editAchieveText");
            
            if(titleEl) titleEl.innerHTML = '<i class="fas fa-book"></i> ' + escapeHtml(project.name) + ' – Full Narrative';
            if(contentDiv) {
                contentDiv.innerHTML = '<div style="margin-bottom: 20px; background:#fafcf9; padding:14px; border-radius:16px;">' +
                    '<strong>📌 Description & Methodology:</strong><br>' + escapeHtml(project.desc || "No description provided.") +
                    '</div>' +
                    '<div style="margin-bottom: 20px; background:#fafcf9; padding:14px; border-radius:16px;">' +
                    '<strong>🏆 Key Achievements / Milestones:</strong><br>' + escapeHtml(project.achievements || "Not yet reported.") +
                    '</div>' +
                    '<div style="font-size:0.85rem; color:#4f7767;">' +
                    '<strong>📍 Details:</strong> Region: ' + escapeHtml(project.region || "—") + ' | Activity Code: ' + escapeHtml(project.code || "—") + 
                    ' | Status: ' + project.status + ' | Timeline: ' + (project.start || "—") + ' to ' + (project.end || "—") + 
                    ' | Partners: ' + escapeHtml(project.partners || "—") + '</div>';
            }
            if(editDesc) editDesc.value = project.desc || "";
            if(editAchieve) editAchieve.value = project.achievements || "";
            if(editArea) editArea.style.display = "none";
            if(detailCard) detailCard.style.display = "block";
            detailCard.scrollIntoView({ behavior: "smooth" });
        }

        function updateStats() {
            var total = projects.length;
            var active = 0;
            var completed = 0;
            for(var i = 0; i < projects.length; i++) {
                if(projects[i].status === "In Progress") active++;
                if(projects[i].status === "Completed") completed++;
            }
            var totalEl = document.getElementById("totalProjectsStat");
            var activeEl = document.getElementById("activeProjectsStat");
            var completedEl = document.getElementById("completedProjectsStat");
            if(totalEl) totalEl.innerText = total;
            if(activeEl) activeEl.innerText = active;
            if(completedEl) completedEl.innerText = completed;
        }

        function escapeHtml(str) {
            if(!str) return '';
            return str.replace(/[&<>]/g, function(m) {
                if(m === '&') return '&amp;';
                if(m === '<') return '&lt;';
                if(m === '>') return '&gt;';
                return m;
            });
        }

        // Event handlers
        document.getElementById("registerProjBtn").addEventListener("click", function() {
            var name = document.getElementById("projName").value.trim();
            if(!name) { alert("Project Title is required"); return; }
            var region = document.getElementById("projRegion").value;
            var budgetVal = document.getElementById("projBudget").value;
            var budget = "";
            if(budgetVal && !isNaN(parseFloat(budgetVal))) budget = parseFloat(budgetVal);
            var code = document.getElementById("projCode").value;
            var start = document.getElementById("projStart").value;
            var end = document.getElementById("projEnd").value;
            var status = document.getElementById("projStatus").value;
            var partners = document.getElementById("projPartners").value;
            var desc = document.getElementById("projDesc").value;
            var achievements = document.getElementById("projAchievements").value;
            
            addProject({
                name: name,
                region: region,
                budget: budget,
                code: code,
                start: start,
                end: end,
                status: status,
                partners: partners,
                desc: desc,
                achievements: achievements
            });
            
            document.getElementById("projName").value = "";
            document.getElementById("projRegion").value = "";
            document.getElementById("projBudget").value = "";
            document.getElementById("projCode").value = "";
            document.getElementById("projStart").value = "";
            document.getElementById("projEnd").value = "";
            document.getElementById("projPartners").value = "";
            document.getElementById("projDesc").value = "";
            document.getElementById("projAchievements").value = "";
            
            alert("✅ Project \"" + name + "\" registered successfully.");
            document.querySelector('[data-panel="listPanel"]').click();
        });

        document.getElementById("clearFormBtn").addEventListener("click", function() {
            document.getElementById("projName").value = "";
            document.getElementById("projRegion").value = "";
            document.getElementById("projBudget").value = "";
            document.getElementById("projCode").value = "";
            document.getElementById("projStart").value = "";
            document.getElementById("projEnd").value = "";
            document.getElementById("projPartners").value = "";
            document.getElementById("projDesc").value = "";
            document.getElementById("projAchievements").value = "";
        });

        document.getElementById("exportCsvBtn").addEventListener("click", function() {
            var csv = "ID,Project Name,Region,Budget,Code,Status,Start Date,End Date,Partners,Description,Achievements\n";
            for(var i = 0; i < projects.length; i++) {
                var p = projects[i];
                csv += "\"" + p.id + "\",\"" + (p.name || "").replace(/"/g, '""') + "\",\"" + (p.region || "").replace(/"/g, '""') + "\",\"" + (p.budget || "") + "\",\"" + (p.code || "").replace(/"/g, '""') + "\",\"" + (p.status || "") + "\",\"" + (p.start || "") + "\",\"" + (p.end || "") + "\",\"" + (p.partners || "").replace(/"/g, '""') + "\",\"" + ((p.desc || "").replace(/"/g, '""').replace(/\n/g,' ')) + "\",\"" + ((p.achievements || "").replace(/"/g, '""').replace(/\n/g,' ')) + "\"\n";
            }
            var blob = new Blob([csv], {type: "text/csv"}); 
            var a = document.createElement("a");
            a.href = URL.createObjectURL(blob); 
            a.download = "pmis_narratives_export.csv"; 
            a.click(); 
            URL.revokeObjectURL(a.href);
        });

        document.getElementById("editNarrativeBtn").addEventListener("click", function() {
            var editArea = document.getElementById("editNarrativeArea");
            if(editArea) editArea.style.display = "block";
        });

        document.getElementById("saveNarrativeEditBtn").addEventListener("click", function() {
            if(currentNarrativeProjectId) {
                var newDesc = document.getElementById("editDescText") ? document.getElementById("editDescText").value : "";
                var newAchieve = document.getElementById("editAchieveText") ? document.getElementById("editAchieveText").value : "";
                updateProject(currentNarrativeProjectId, { desc: newDesc, achievements: newAchieve });
                var editArea = document.getElementById("editNarrativeArea");
                if(editArea) editArea.style.display = "none";
                showNarrativeDetail(currentNarrativeProjectId);
            }
        });

        document.getElementById("cancelEditBtn").addEventListener("click", function() {
            var editArea = document.getElementById("editNarrativeArea");
            if(editArea) editArea.style.display = "none";
        });

        document.getElementById("closeNarrativeBtn").addEventListener("click", function() {
            var detailCard = document.getElementById("narrativeDetailCard");
            if(detailCard) detailCard.style.display = "none";
            currentNarrativeProjectId = null;
        });

        var navBtns = document.querySelectorAll('.nav-btn');
        var panels = document.querySelectorAll('.panel');
        for(var i = 0; i < navBtns.length; i++) {
            navBtns[i].addEventListener('click', function() {
                var panelId = this.getAttribute('data-panel');
                for(var j = 0; j < navBtns.length; j++) {
                    navBtns[j].classList.remove('active');
                }
                this.classList.add('active');
                for(var k = 0; k < panels.length; k++) {
                    panels[k].classList.remove('active-panel');
                }
                var activePanel = document.getElementById(panelId);
                if(activePanel) activePanel.classList.add('active-panel');
                if(panelId === 'narrativePanel') {
                    renderNarrativeList();
                    updateStats();
                    var detailCard = document.getElementById("narrativeDetailCard");
                    if(detailCard) detailCard.style.display = "none";
                    currentNarrativeProjectId = null;
                }
                if(panelId === 'listPanel') renderProjectList();
            });
        }

        loadProjects();
    })();
</script>
</body>
</html>
