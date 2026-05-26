---
layout: default
title: Home
---

<div class="not-prose">

  <!-- Hero -->
  <div class="pt-4 pb-16 sm:pt-8 sm:pb-20">
    <div class="inline-flex items-center gap-2 rounded-full bg-indigo-50 px-3 py-1 text-xs font-medium text-indigo-700 ring-1 ring-inset ring-indigo-200 mb-6">
      Mac app · Early access
    </div>
    <h1 class="text-4xl sm:text-5xl font-bold tracking-tight text-stone-900 leading-tight max-w-2xl">
      Project intelligence<br>for small teams
    </h1>
    <p class="mt-5 text-xl text-stone-600 max-w-2xl leading-relaxed">
      Studio is a Mac app that gives everyone on your team a shared, AI-aware workspace built around your project repo — docs, data, tasks, and context all in one place.
    </p>
    <div class="mt-8 flex flex-wrap items-center gap-3">
      {% if site.download_mac_url %}
      <a href="{{ site.download_mac_url }}" class="inline-flex items-center justify-center rounded-lg bg-indigo-600 px-6 py-3 text-base font-semibold text-white shadow-sm transition-colors hover:bg-indigo-500" download rel="noopener noreferrer">
        Download for Mac
      </a>
      {% endif %}
      {% if site.releases_page_url %}
      <a href="{{ site.releases_page_url }}" class="inline-flex items-center justify-center rounded-lg border border-stone-300 bg-white px-6 py-3 text-base font-semibold text-stone-700 shadow-sm transition-colors hover:bg-stone-50" rel="noopener noreferrer" target="_blank">
        Release notes
      </a>
      {% endif %}
    </div>
  </div>

  <!-- Divider -->
  <hr class="border-stone-200 mb-16">

  <!-- Problem statement -->
  <div class="mb-16">
    <h2 class="text-2xl font-bold text-stone-900 mb-4">The problem with how small teams manage work</h2>
    <div class="grid sm:grid-cols-3 gap-6">
      <div class="rounded-xl border border-stone-200 bg-white p-5">
        <p class="text-sm font-semibold text-stone-800 mb-2">Your AI has no memory</p>
        <p class="text-sm text-stone-600">Every new chat session starts from zero. You re-explain context, re-describe the project, re-establish what matters. The AI never knows your business the way a good teammate would.</p>
      </div>
      <div class="rounded-xl border border-stone-200 bg-white p-5">
        <p class="text-sm font-semibold text-stone-800 mb-2">Docs and data live in different places</p>
        <p class="text-sm text-stone-600">Notion has your planning docs. Airtable has your data. Slack has the decisions. Spreadsheets have the numbers. Nobody has the full picture, and the AI sees none of it.</p>
      </div>
      <div class="rounded-xl border border-stone-200 bg-white p-5">
        <p class="text-sm font-semibold text-stone-800 mb-2">Non-technical people are locked out</p>
        <p class="text-sm text-stone-600">If your project lives in a code editor, the people who aren't developers can't participate. They wait for reports, summaries, and updates instead of having direct access.</p>
      </div>
    </div>
  </div>

  <!-- What Studio is -->
  <div class="mb-16">
    <h2 class="text-2xl font-bold text-stone-900 mb-4">What Studio does</h2>
    <p class="text-stone-600 mb-8 max-w-2xl">Studio treats your project as a git repo — a structured folder of docs, scripts, and data. It gives everyone on your team an interface for that repo: an AI that knows the full context, live data from your business systems, and a shared place to read, write, and decide.</p>
    <div class="grid sm:grid-cols-2 gap-5">

      <div class="rounded-xl border border-stone-200 bg-white p-5 flex gap-4">
        <div class="text-2xl mt-0.5">🧠</div>
        <div>
          <p class="text-sm font-semibold text-stone-900 mb-1">Persistent project context</p>
          <p class="text-sm text-stone-600">Load your project's docs, README, status notes, and task list into every chat session. The AI always knows who you are, what you're building, and what matters right now.</p>
        </div>
      </div>

      <div class="rounded-xl border border-stone-200 bg-white p-5 flex gap-4">
        <div class="text-2xl mt-0.5">📊</div>
        <div>
          <p class="text-sm font-semibold text-stone-900 mb-1">Live business data on the dashboard</p>
          <p class="text-sm text-stone-600">Scripts pull live data from Shopify, Klaviyo, Amazon, QuickBooks, and other APIs. Results appear as visualized dashboards — revenue, orders, inventory — updated on demand.</p>
        </div>
      </div>

      <div class="rounded-xl border border-stone-200 bg-white p-5 flex gap-4">
        <div class="text-2xl mt-0.5">📝</div>
        <div>
          <p class="text-sm font-semibold text-stone-900 mb-1">Docs the AI can read and write</p>
          <p class="text-sm text-stone-600">Your planning docs, meeting notes, SOPs, and decisions live in Markdown files in the repo. The AI can read them for context and write new ones when you ask.</p>
        </div>
      </div>

      <div class="rounded-xl border border-stone-200 bg-white p-5 flex gap-4">
        <div class="text-2xl mt-0.5">👥</div>
        <div>
          <p class="text-sm font-semibold text-stone-900 mb-1">Shared across your team</p>
          <p class="text-sm text-stone-600">Because the project is a git repo, everything is versioned and shareable. Everyone on the team — technical or not — can open Studio and be oriented in the project.</p>
        </div>
      </div>

      <div class="rounded-xl border border-stone-200 bg-white p-5 flex gap-4">
        <div class="text-2xl mt-0.5">🔑</div>
        <div>
          <p class="text-sm font-semibold text-stone-900 mb-1">Secure API key management</p>
          <p class="text-sm text-stone-600">Environment variables for your data scripts are stored locally in a git-ignored .env file — never committed. Studio's settings panel manages them per project.</p>
        </div>
      </div>

      <div class="rounded-xl border border-stone-200 bg-white p-5 flex gap-4">
        <div class="text-2xl mt-0.5">🔧</div>
        <div>
          <p class="text-sm font-semibold text-stone-900 mb-1">The AI builds the scripts too</p>
          <p class="text-sm text-stone-600">Ask the AI to connect to a new data source and it writes the script, the visualization config, and the setup instructions. You run it when you're ready.</p>
        </div>
      </div>

    </div>
  </div>

  <!-- Who it's for -->
  <div class="mb-16">
    <h2 class="text-2xl font-bold text-stone-900 mb-4">Who it's for</h2>
    <div class="grid sm:grid-cols-3 gap-5">

      <div class="rounded-xl bg-stone-900 text-white p-6">
        <p class="text-sm font-semibold text-indigo-300 mb-2 uppercase tracking-wide">Product businesses</p>
        <p class="text-sm text-stone-300 leading-relaxed">You sell physical products, manage inventory, and run marketing across multiple channels. You need a dashboard that pulls Shopify, Amazon, email, and wholesale data together — with an AI that understands the business, not just the spreadsheet.</p>
      </div>

      <div class="rounded-xl bg-stone-900 text-white p-6">
        <p class="text-sm font-semibold text-indigo-300 mb-2 uppercase tracking-wide">Consulting practices</p>
        <p class="text-sm text-stone-300 leading-relaxed">You manage multiple clients, each with their own context, documents, and deliverables. Studio gives each engagement its own project with shared context — so the AI knows the client, the history, and the current priorities.</p>
      </div>

      <div class="rounded-xl bg-stone-900 text-white p-6">
        <p class="text-sm font-semibold text-indigo-300 mb-2 uppercase tracking-wide">Technical projects with mixed teams</p>
        <p class="text-sm text-stone-300 leading-relaxed">Your project has engineers, project managers, and stakeholders who don't use code editors. Studio gives everyone access to the project's knowledge — decisions, status, data — without requiring a terminal.</p>
      </div>

    </div>
  </div>

  <!-- How it's different -->
  <div class="mb-16">
    <h2 class="text-2xl font-bold text-stone-900 mb-2">How it's different</h2>
    <p class="text-stone-600 mb-6 max-w-2xl">Studio occupies a specific space that other tools don't fill.</p>
    <div class="overflow-x-auto">
      <table class="w-full text-sm border-collapse">
        <thead>
          <tr class="bg-stone-100">
            <th class="text-left px-4 py-3 font-semibold text-stone-700 rounded-tl-lg"></th>
            <th class="text-left px-4 py-3 font-semibold text-stone-700">Persistent project context</th>
            <th class="text-left px-4 py-3 font-semibold text-stone-700">Live business data</th>
            <th class="text-left px-4 py-3 font-semibold text-stone-700">Non-technical access</th>
            <th class="text-left px-4 py-3 font-semibold text-stone-700 rounded-tr-lg">Shared by team</th>
          </tr>
        </thead>
        <tbody>
          <tr class="border-t border-stone-200 bg-indigo-50">
            <td class="px-4 py-3 font-semibold text-indigo-700">Studio</td>
            <td class="px-4 py-3 text-stone-700">✓</td>
            <td class="px-4 py-3 text-stone-700">✓</td>
            <td class="px-4 py-3 text-stone-700">✓</td>
            <td class="px-4 py-3 text-stone-700">✓</td>
          </tr>
          <tr class="border-t border-stone-200">
            <td class="px-4 py-3 text-stone-600">Cursor / VS Code</td>
            <td class="px-4 py-3 text-stone-400">Partial</td>
            <td class="px-4 py-3 text-stone-400">—</td>
            <td class="px-4 py-3 text-stone-400">—</td>
            <td class="px-4 py-3 text-stone-400">—</td>
          </tr>
          <tr class="border-t border-stone-200">
            <td class="px-4 py-3 text-stone-600">Notion / Confluence</td>
            <td class="px-4 py-3 text-stone-400">—</td>
            <td class="px-4 py-3 text-stone-400">—</td>
            <td class="px-4 py-3 text-stone-400">✓</td>
            <td class="px-4 py-3 text-stone-400">✓</td>
          </tr>
          <tr class="border-t border-stone-200">
            <td class="px-4 py-3 text-stone-600">Claude.ai / ChatGPT</td>
            <td class="px-4 py-3 text-stone-400">—</td>
            <td class="px-4 py-3 text-stone-400">—</td>
            <td class="px-4 py-3 text-stone-400">✓</td>
            <td class="px-4 py-3 text-stone-400">—</td>
          </tr>
          <tr class="border-t border-stone-200">
            <td class="px-4 py-3 text-stone-600">Airtable / Retool</td>
            <td class="px-4 py-3 text-stone-400">—</td>
            <td class="px-4 py-3 text-stone-400">✓</td>
            <td class="px-4 py-3 text-stone-400">✓</td>
            <td class="px-4 py-3 text-stone-400">✓</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- Built on git -->
  <div class="mb-16 rounded-2xl bg-stone-900 text-white p-8 sm:p-10">
    <h2 class="text-2xl font-bold mb-3">Built on git, not a database</h2>
    <p class="text-stone-300 leading-relaxed max-w-2xl mb-6">Everything in Studio — your docs, tasks, data, scripts, and notes — lives in a git repository you own. That means version history is automatic, collaboration uses the workflows your team already knows, and you are never locked in. Close Studio and you still have your files.</p>
    <p class="text-stone-400 text-sm">No proprietary format. No cloud sync required. No vendor lock-in.</p>
  </div>

  <!-- Download CTA -->
  <div class="mb-8 text-center py-12 rounded-2xl border border-stone-200 bg-white">
    <h2 class="text-2xl font-bold text-stone-900 mb-2">Try Studio</h2>
    <p class="text-stone-600 mb-6 max-w-md mx-auto">Mac app, free to download. Bring your own Anthropic API key. Your projects stay on your machine.</p>
    <div class="flex flex-wrap items-center justify-center gap-3">
      {% if site.download_mac_url %}
      <a href="{{ site.download_mac_url }}" class="inline-flex items-center justify-center rounded-lg bg-indigo-600 px-6 py-3 text-base font-semibold text-white shadow-sm transition-colors hover:bg-indigo-500" download rel="noopener noreferrer">
        Download for Mac
      </a>
      {% endif %}
      {% if site.studio_repo_url %}
      <a href="{{ site.studio_repo_url }}" class="inline-flex items-center justify-center rounded-lg border border-stone-300 bg-white px-6 py-3 text-base font-semibold text-stone-700 shadow-sm transition-colors hover:bg-stone-50" rel="noopener noreferrer" target="_blank">
        Source on GitHub
      </a>
      {% endif %}
    </div>
  </div>

</div>
