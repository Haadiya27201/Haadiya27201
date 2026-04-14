name: Metrics
on:
  schedule: [{cron: "0 */12 * * *"}]
  workflow_dispatch:

jobs:
  github-metrics:
    runs-on: ubuntu-latest
    steps:
      - uses: lowlighter/metrics@latest
        with:
          filename: github-metrics.svg
          token: ${{ secrets.GITHUB_TOKEN }}

          # 🎨 Base
          user: haadiya-hasan
          template: classic
          base: header, activity, community, repositories
          config_timezone: Asia/Kolkata

          # 📊 Languages
          plugin_languages: yes
          plugin_languages_limit: 8
          plugin_languages_sections: most-used
          plugin_languages_indepth: yes

          # 📅 Activity graph
          plugin_activity: yes

          # 🔥 Streak / habits
          plugin_habits: yes
          plugin_habits_days: 14
          plugin_habits_facts: yes

          # 📆 Contributions calendar (3D blocks style)
          plugin_isocalendar: yes

          # 🎵 Music (yes that random Apple Music thing)
          plugin_music: yes
          plugin_music_provider: apple
          plugin_music_limit: 2

          # 📈 Lines of code, commits
          plugin_lines: yes

          # ⭐ Stars, followers
          plugin_followup: yes

          # 📌 Featured repo section
          plugin_projects: yes
          plugin_projects_limit: 1

          # ⚡ Achievements
          plugin_achievements: yes

          # 🧠 Coding habits per time of day
          plugin_wakatime: no
