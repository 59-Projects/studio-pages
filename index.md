---
layout: default
title: Home
---

# Studio

{{ site.description }}

<div class="not-prose mt-8 max-w-xl">
  <p class="text-lg text-stone-600">Install the Studio Mac app (.dmg). The button starts a direct download from the latest GitHub Release.</p>
  <div class="mt-6 flex flex-wrap items-center gap-3">
    {% if site.download_mac_url %}
    <a href="{{ site.download_mac_url }}" class="inline-flex items-center justify-center rounded-lg bg-indigo-600 px-5 py-3 text-base font-semibold text-white shadow-sm transition-colors hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600" download rel="noopener noreferrer">Download Mac app (.dmg)</a>
    {% endif %}
    {% if site.releases_page_url %}
    <a href="{{ site.releases_page_url }}" class="inline-flex items-center justify-center rounded-lg border border-stone-300 bg-white px-5 py-3 text-base font-semibold text-stone-800 shadow-sm transition-colors hover:bg-stone-50" rel="noopener noreferrer" target="_blank">All releases</a>
    {% endif %}
    {% if site.studio_repo_url %}
    <a href="{{ site.studio_repo_url }}" class="inline-flex items-center justify-center rounded-lg border border-stone-300 bg-white px-5 py-3 text-base font-semibold text-stone-800 shadow-sm transition-colors hover:bg-stone-50" rel="noopener noreferrer" target="_blank">Source on GitHub</a>
    {% endif %}
  </div>
</div>
