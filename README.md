# Visit https://github.com/lowlighter/metrics/blob/master/action.yml for full reference
name: Metrics
on:
  # Schedule updates (each hour)
  schedule: [{cron: "0 * * * *"}]
  # Lines below let you run workflow manually and on each commit
  workflow_dispatch:
  push: {branches: ["master", "main"]}
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    steps:
      - uses: lowlighter/metrics@latest
        with:
          # Your GitHub token
          # The following scopes are required:
          #  - public_access (default scope)
          #  - repo
          # The following additional scopes may be required:
          #  - read:org  (for organization related metrics)
          #  - read:user (for user related data)
          #  - repo      (optional, if you want to include private repositories)
          token: ${{ secrets.METRICS_TOKEN }}

          # Options
          user: Tanmay-Tiwaricyber
          template: classic
          base: header, activity, community, repositories, metadata
          config_timezone: Asia/Calcutta
          plugin_achievements: yes
          plugin_achievements_display: compact
          plugin_achievements_secrets: yes
          plugin_achievements_threshold: X
          plugin_gists: yes
          plugin_habits: yes
          plugin_habits_charts_type: chartist
          plugin_habits_days: 14
          plugin_habits_facts: yes
          plugin_habits_from: 200
          plugin_introduction: yes
          plugin_introduction_title: yes
          plugin_isocalendar: yes
          plugin_isocalendar_duration: half-year
          plugin_languages: yes
          plugin_languages_analysis_timeout: 15
          plugin_languages_categories: markup, programming
          plugin_languages_colors: github
          plugin_languages_limit: 8
          plugin_languages_recent_categories: markup, programming
          plugin_languages_recent_days: 14
          plugin_languages_recent_load: 300
          plugin_languages_sections: most-used
          plugin_languages_threshold: 0%
          plugin_lines: yes
          plugin_pagespeed: yes
          plugin_pagespeed_detailed: yes
          plugin_pagespeed_url: https://remote-coders-2022.netlify.app/
          plugin_repositories: 100
          plugin_repositories: yes
          plugin_repositories_affiliations: owner
          plugin_repositories_batch: 100
          plugin_skyline: yes
          plugin_skyline_compatibility: yes
          plugin_skyline_frames: 60
          plugin_skyline_quality: 0.5
          plugin_skyline_year: 2021
          plugin_stars: yes
          plugin_stars_limit: 4
          plugin_support: yes
          plugin_traffic: yes
