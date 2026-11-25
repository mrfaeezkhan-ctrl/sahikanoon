<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>SahiKanoon — Documents, Schemes, Laws & Constitution</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
</head>
<body class="bg-slate-950 text-slate-100 min-h-screen font-sans">

  <!-- Header -->
  <header class="sticky top-0 z-50 bg-slate-900/95 backdrop-blur border-b border-slate-800">
    <div class="max-w-6xl mx-auto px-4 py-3 flex flex-wrap items-center justify-between gap-3">
      <div>
        <h1 class="text-xl font-bold text-amber-400 tracking-tight">⚖️ SahiKanoon</h1>
        <p class="text-xs text-slate-400">India & Maharashtra Citizen Rights, Schemes & Documents</p>
      </div>
      <div class="flex items-center gap-2">
        <label for="langSelect" class="text-xs text-slate-400">Language:</label>
        <select id="langSelect" class="bg-slate-800 border border-slate-700 text-sm rounded-lg px-2.5 py-1.5 text-white">
          <option value="hinglish">Hinglish</option>
          <option value="en">English</option>
          <option value="hi">हिंदी (Hindi)</option>
          <option value="mr">मराठी (Marathi)</option>
        </select>
      </div>
    </div>

    <!-- Main Navigation Tabs -->
    <div class="max-w-6xl mx-auto px-4 pb-3 flex gap-2 overflow-x-auto">
      <button onclick="switchTab('documents')" id="tab-documents" class="tab-btn px-4 py-2 rounded-lg text-sm font-medium bg-amber-500 text-slate-950 whitespace-nowrap">📄 Documents</button>
      <button onclick="switchTab('schemes')" id="tab-schemes" class="tab-btn px-4 py-2 rounded-lg text-sm font-medium bg-slate-800 text-slate-300 hover:bg-slate-700 whitespace-nowrap">🎓 Schemes & Scholarships</button>
      <button onclick="switchTab('laws')" id="tab-laws" class="tab-btn px-4 py-2 rounded-lg text-sm font-medium bg-slate-800 text-slate-300 hover:bg-slate-700 whitespace-nowrap">⚖️ Laws & Rights</button>
      <button onclick="switchTab('cybercrime')" id="tab-cybercrime" class="tab-btn px-4 py-2 rounded-lg text-sm font-medium bg-slate-800 text-slate-300 hover:bg-slate-700 whitespace-nowrap">🛡️ Cybercrime & Security</button>
      <button onclick="switchTab('constitution')" id="tab-constitution" class="tab-btn px-4 py-2 rounded-lg text-sm font-medium bg-slate-800 text-slate-300 hover:bg-slate-700 whitespace-nowrap">📜 Constitution</button>
    </div>
  </header>

  <!-- Main Content -->
  <main class="max-w-6xl mx-auto px-4 py-6">
    <!-- Search & Sub-filters -->
    <div class="mb-6 space-y-3">
      <input
        id="searchInput"
        type="text"
        placeholder="Search Aadhaar, PAN, Scholarship, Traffic, Cybercrime, Article 21..."
        class="w-full bg-slate-900 border border-slate-700 rounded-xl px-4 py-3 text-sm text-white placeholder-slate-400 focus:outline-none focus:border-amber-400"
      />
      <div id="subFilters" class="flex flex-wrap gap-2"></div>
    </div>

    <!-- Emergency Banner for Cybercrime -->
    <div id="cyberBanner" class="hidden mb-6 bg-red-950/60 border border-red-700/60 rounded-xl p-4 flex flex-wrap items-center justify-between gap-3">
      <div>
        <h2 class="font-bold text-red-300 text-sm">🚨 Cyber Fraud Helpline: Call 1930 (24x7)</h2>
        <p class="text-xs text-red-200/80">UPI/Bank fraud hone ke 1 ghante (Golden Hour) ke andar 1930 par call karein ya cybercrime.gov.in par report karein.</p>
      </div>
      <a href="https://cybercrime.gov.in/" target="_blank" class="px-3 py-1.5 bg-red-600 hover:bg-red-500 text-white text-xs font-semibold rounded-lg">Report Now ↗</a>
    </div>

    <!-- Status / Loader -->
    <div id="statusMsg" class="text-center py-10 text-slate-400 text-sm">Loading SahiKanoon database...</div>

    <!-- Cards Container -->
    <div id="cardsGrid" class="grid grid-cols-1 md:grid-cols-2 gap-4"></div>
  </main>

  <footer class="border-t border-slate-800 mt-12 py-6 text-center text-xs text-slate-500">
    SahiKanoon • Citizen Legal & Government Awareness Platform • Always verify on official govt portals linked on each card.
  </footer>

  <script>
    // ============================================================
    // SUPABASE CONNECTION (Sirf neeche apna Publishable Key paste karein)
    // ============================================================
    const SUPABASE_URL = 'https://alsrmtwjeljrjjhsgkex.supabase.co';
    const SUPABASE_KEY = 'sb_publishable_LNSGOQ2bGVPjA-baVD_2zg_TA4LnAwF';

    const db = window.supabase.createClient(SUPABASE_URL, SUPABASE_KEY);

    let currentTab = 'documents';
    let currentLang = 'hinglish';
    let currentFilter = 'all';
    let cache = { documents: [], schemes: [], laws: [], constitution: [] };

    const langSelect = document.getElementById('langSelect');
    const searchInput = document.getElementById('searchInput');
    const cardsGrid = document.getElementById('cardsGrid');
    const statusMsg = document.getElementById('statusMsg');
    const subFilters = document.getElementById('subFilters');
    const cyberBanner = document.getElementById('cyberBanner');

    langSelect.addEventListener('change', (e) => {
      currentLang = e.target.value;
      render();
    });

    searchInput.addEventListener('input', () => render());

    function getLocalized(item, field) {
      return item[`${field}_${currentLang}`] || item[`${field}_hinglish`] || item[`${field}_en`] || '';
    }

    function speakText(text) {
      if (!('speechSynthesis' in window)) return alert('Voice read-aloud is not supported in this browser.');
      window.speechSynthesis.cancel();
      const utter = new SpeechSynthesisUtterance(text);
      utter.lang = currentLang === 'hi' ? 'hi-IN' : currentLang === 'mr' ? 'mr-IN' : 'en-IN';
      window.speechSynthesis.speak(utter);
    }

    function switchTab(tab) {
      currentTab = tab;
      currentFilter = 'all';
      document.querySelectorAll('.tab-btn').forEach(btn => {
        btn.className = 'tab-btn px-4 py-2 rounded-lg text-sm font-medium bg-slate-800 text-slate-300 hover:bg-slate-700 whitespace-nowrap';
      });
      document.getElementById(`tab-${tab}`).className = 'tab-btn px-4 py-2 rounded-lg text-sm font-medium bg-amber-500 text-slate-950 whitespace-nowrap';
      cyberBanner.classList.toggle('hidden', tab !== 'cybercrime');
      renderSubFilters();
      render();
    }

    function setFilter(val) {
      currentFilter = val;
      renderSubFilters();
      render();
    }

    function renderSubFilters() {
      let options = [];
      if (currentTab === 'schemes') {
        options = [
          { id: 'all', label: 'All Schemes' },
          { id: 'Scholarship', label: '🎓 Scholarships' },
          { id: 'Maharashtra', label: 'Maharashtra' },
          { id: 'Central', label: 'Central Govt' },
          { id: 'active', label: '✅ Active' },
          { id: 'inactive', label: '⛔ Closed / Inactive' }
        ];
      } else if (currentTab === 'laws') {
        options = [
          { id: 'all', label: 'All Laws' },
          { id: 'traffic', label: '🚦 Traffic (MVA)' },
          { id: 'criminal', label: '🚓 Criminal (BNS/BNSS)' },
          { id: 'office', label: '💼 Office & Salary' },
          { id: 'document', label: '📄 RTI & RTS Rights' }
        ];
      } else if (currentTab === 'documents') {
        options = [
          { id: 'all', label: 'All 17 Documents' },
          { id: 'Central Identity', label: 'Central ID' },
          { id: 'Maharashtra Certificate', label: 'Maharashtra Certs' },
          { id: 'Vehicle & Driving', label: 'Driving (LL/DL)' },
          { id: 'Civil Registration', label: 'Birth / Marriage / Gazette' }
        ];
      }
      subFilters.innerHTML = options.map(o => `
        <button onclick="setFilter('${o.id}')" class="px-3 py-1 rounded-full text-xs font-medium border ${
          currentFilter === o.id
            ? 'bg-amber-500/20 border-amber-400 text-amber-300'
            : 'bg-slate-900 border-slate-700 text-slate-400 hover:text-white'
        }">${o.label}</button>
      `).join('');
    }

    async function loadAllData() {
      try {
        const [docs, schemes, laws, constitution] = await Promise.all([
          db.from('documents').select('*').order('id'),
          db.from('schemes').select('*').order('id'),
          db.from('laws').select('*').order('id'),
          db.from('constitution').select('*').order('id')
        ]);

        if (docs.error) throw docs.error;
        cache.documents = docs.data || [];
        cache.schemes = schemes.data || [];
        cache.laws = laws.data || [];
        cache.constitution = constitution.data || [];

        statusMsg.classList.add('hidden');
        renderSubFilters();
        render();
      } catch (err) {
        statusMsg.innerHTML = `<span class="text-red-400">Database connect nahi hua. Check karein ki aapne <b>SUPABASE_KEY</b> sahi paste kiya hai. (${err.message})</span>`;
      }
    }

    function render() {
      const q = searchInput.value.trim().toLowerCase();
      let html = '';

      if (currentTab === 'documents') {
        let list = cache.documents.filter(d => {
          const matchFilter = currentFilter === 'all' || d.category === currentFilter;
          const matchSearch = !q || JSON.stringify(d).toLowerCase().includes(q);
          return matchFilter && matchSearch;
        });

        html = list.map(d => `
          <div class="bg-slate-900 border border-slate-800 rounded-xl p-5 flex flex-col justify-between gap-3">
            <div>
              <div class="flex items-start justify-between gap-2 mb-2">
                <h3 class="font-bold text-amber-300 text-base">${d.doc_name}</h3>
                <span class="text-[11px] px-2 py-0.5 rounded bg-slate-800 text-slate-300 whitespace-nowrap">${d.state}</span>
              </div>
              <p class="text-xs text-emerald-400 font-medium mb-2">💰 Fee: ${d.official_fee}</p>
              <p class="text-xs text-slate-400 mb-3">⏱️ Time: ${d.processing_time} • Mode: ${d.apply_mode}</p>
              <div class="space-y-2 text-xs text-slate-300">
                <p><b class="text-white">Required Docs:</b> ${d.required_docs}</p>
                <p><b class="text-white">Steps:</b> ${d.making_steps}</p>
                <p><b class="text-white">Track/Download:</b> ${d.track_download_steps}</p>
              </div>
            </div>
            <div class="flex items-center justify-between pt-3 border-t border-slate-800">
              <button onclick="speakText(\`${(d.doc_name + '. ' + d.making_steps).replace(/`/g, '')}\`)" class="text-xs px-3 py-1.5 rounded-lg bg-slate-800 hover:bg-slate-700 text-slate-200">🔊 Suniye</button>
              <a href="${d.official_portal_url}" target="_blank" class="text-xs px-3 py-1.5 rounded-lg bg-amber-500 hover:bg-amber-400 text-slate-950 font-semibold">Official Portal ↗</a>
            </div>
          </div>
        `).join('');
      }

      else if (currentTab === 'schemes') {
        let list = cache.schemes.filter(s => {
          const matchFilter =
            currentFilter === 'all' ||
            (currentFilter === 'Scholarship' && s.category === 'Scholarship') ||
            (currentFilter === 'Maharashtra' && s.state === 'Maharashtra') ||
            (currentFilter === 'Central' && s.level === 'central') ||
            (currentFilter === 'active' && s.status === 'active') ||
            (currentFilter === 'inactive' && s.status === 'inactive');
          const matchSearch = !q || JSON.stringify(s).toLowerCase().includes(q);
          return matchFilter && matchSearch;
        });

        html = list.map(s => {
          const title = getLocalized(s, 'title');
          const isClosed = s.status === 'inactive';
          return `
          <div class="bg-slate-900 border ${isClosed ? 'border-red-900/60' : 'border-slate-800'} rounded-xl p-5 flex flex-col justify-between gap-3">
            <div>
              <div class="flex flex-wrap items-center gap-2 mb-2">
                <span class="text-[11px] px-2 py-0.5 rounded font-semibold ${isClosed ? 'bg-red-900/60 text-red-300' : 'bg-emerald-900/60 text-emerald-300'}">${isClosed ? '⛔ INACTIVE / CLOSED' : '✅ ACTIVE'}</span>
                <span class="text-[11px] px-2 py-0.5 rounded bg-slate-800 text-slate-300">${s.state}</span>
                <span class="text-[11px] px-2 py-0.5 rounded bg-amber-500/20 text-amber-300">${s.category}</span>
              </div>
              <h3 class="font-bold text-white text-base mb-2">${title}</h3>
              <div class="space-y-2 text-xs text-slate-300">
                <p><b class="text-amber-300">Benefit:</b> ${s.benefit_summary}</p>
                <p><b class="text-white">Eligibility:</b> ${s.eligibility}</p>
                <p><b class="text-white">Documents:</b> ${s.documents_required}</p>
                <p><b class="text-white">How to Apply:</b> ${s.apply_steps}</p>
              </div>
            </div>
            <div class="flex items-center justify-between pt-3 border-t border-slate-800">
              <button onclick="speakText(\`${(title + '. ' + s.benefit_summary).replace(/`/g, '')}\`)" class="text-xs px-3 py-1.5 rounded-lg bg-slate-800 hover:bg-slate-700 text-slate-200">🔊 Suniye</button>
              <a href="${s.proof_url}" target="_blank" class="text-xs px-3 py-1.5 rounded-lg bg-amber-500 hover:bg-amber-400 text-slate-950 font-semibold">Official Portal ↗</a>
            </div>
          </div>`;
        }).join('');
      }

      else if (currentTab === 'laws' || currentTab === 'cybercrime') {
        let list = cache.laws.filter(l => {
          if (currentTab === 'cybercrime') {
            return l.law_category === 'cybercrime' && (!q || JSON.stringify(l).toLowerCase().includes(q));
          } else {
            const notCyber = l.law_category !== 'cybercrime';
            const matchFilter = currentFilter === 'all' || l.law_category === currentFilter;
            const matchSearch = !q || JSON.stringify(l).toLowerCase().includes(q);
            return notCyber && matchFilter && matchSearch;
          }
        });

        html = list.map(l => {
          const title = getLocalized(l, 'title');
          const summary = getLocalized(l, 'summary');
          return `
          <div class="bg-slate-900 border border-slate-800 rounded-xl p-5 flex flex-col justify-between gap-3">
            <div>
              <div class="flex flex-wrap items-center gap-2 mb-2">
                <span class="text-[11px] px-2 py-0.5 rounded bg-indigo-900/60 text-indigo-300 font-semibold">${l.act_name} — ${l.section_number}</span>
                ${l.show_to_officer ? '<span class="text-[11px] px-2 py-0.5 rounded bg-amber-500/20 text-amber-300">🪪 Show to Officer</span>' : ''}
              </div>
              <h3 class="font-bold text-white text-base mb-2">${title}</h3>
              <p class="text-xs text-slate-300 mb-3">${summary}</p>
              <div class="space-y-1.5 text-xs text-slate-300 bg-slate-950/70 p-3 rounded-lg border border-slate-800">
                <p><b class="text-amber-300">Fine / Penalty:</b> ${l.fine_details}</p>
                <p><b class="text-red-300">Jail Term:</b> ${l.jail_term}</p>
                <p><b class="text-emerald-300">Your Rights / Action:</b> ${l.citizen_rights}</p>
              </div>
            </div>
            <div class="flex items-center justify-between pt-3 border-t border-slate-800">
              <button onclick="speakText(\`${(title + '. ' + summary + ' ' + l.citizen_rights).replace(/`/g, '')}\`)" class="text-xs px-3 py-1.5 rounded-lg bg-slate-800 hover:bg-slate-700 text-slate-200">🔊 Suniye</button>
              <a href="${l.proof_url}" target="_blank" class="text-xs px-3 py-1.5 rounded-lg bg-amber-500 hover:bg-amber-400 text-slate-950 font-semibold">Official Proof ↗</a>
            </div>
          </div>`;
        }).join('');
      }

      else if (currentTab === 'constitution') {
        let list = cache.constitution.filter(c => !q || JSON.stringify(c).toLowerCase().includes(q));
        html = list.map(c => {
          const title = getLocalized(c, 'title');
          const summary = getLocalized(c, 'summary');
          return `
          <div class="bg-slate-900 border border-slate-800 rounded-xl p-5 flex flex-col justify-between gap-3">
            <div>
              <div class="flex flex-wrap items-center gap-2 mb-2">
                <span class="text-[11px] px-2 py-0.5 rounded bg-amber-500/20 text-amber-300 font-semibold">${c.article_number}</span>
                <span class="text-[11px] px-2 py-0.5 rounded bg-slate-800 text-slate-300">${c.part_number} • ${c.part_title}</span>
              </div>
              <h3 class="font-bold text-white text-base mb-2">${title}</h3>
              <p class="text-xs text-slate-300 leading-relaxed">${summary}</p>
            </div>
            <div class="flex items-center justify-between pt-3 border-t border-slate-800">
              <button onclick="speakText(\`${(c.article_number + '. ' + title + '. ' + summary).replace(/`/g, '')}\`)" class="text-xs px-3 py-1.5 rounded-lg bg-slate-800 hover:bg-slate-700 text-slate-200">🔊 Suniye</button>
              <a href="${c.proof_url}" target="_blank" class="text-xs px-3 py-1.5 rounded-lg bg-amber-500 hover:bg-amber-400 text-slate-950 font-semibold">Official Text ↗</a>
            </div>
          </div>`;
        }).join('');
      }

      cardsGrid.innerHTML = html || `<div class="col-span-full text-center py-10 text-slate-400 text-sm">Koi matching result nahi mila.</div>`;
    }

    loadAllData();
  </script>
</body>
</html>
