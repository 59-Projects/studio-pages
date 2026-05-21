---
layout: default
title: Home
---

# Studio

{{ site.description }}

<div class="not-prose mt-8 max-w-xl">
  <p class="text-lg text-stone-600">Install the Mac app from our latest release. Download the <code class="rounded bg-stone-100 px-1.5 py-0.5 text-sm text-stone-800">.dmg</code> or archive for your machine (Apple Silicon or Intel) from the release assets.</p>
  <div class="mt-6 flex flex-wrap items-center gap-3">
    <a href="{{ site.download_page_url }}" class="inline-flex items-center justify-center rounded-lg bg-indigo-600 px-5 py-3 text-base font-semibold text-white shadow-sm transition-colors hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600" rel="noopener noreferrer" target="_blank">Download</a>
    {% if site.studio_repo_url %}
    <a href="{{ site.studio_repo_url }}" class="inline-flex items-center justify-center rounded-lg border border-stone-300 bg-white px-5 py-3 text-base font-semibold text-stone-800 shadow-sm transition-colors hover:bg-stone-50" rel="noopener noreferrer" target="_blank">Source on GitHub</a>
    {% endif %}
  </div>
</div>
