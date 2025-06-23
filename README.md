name: Waka Readme Update

on:
  schedule:
    # Chạy mỗi 6 tiếng
    - cron: '0 */6 * * *'
  workflow_dispatch: # Cho phép chạy thủ công

jobs:
  update-readme:
    name: Update Readme with WakaTime Stats
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: athul/waka-readme@master
        with:
          WAKATIME_API_KEY: ${{ secrets.WAKATIME_API_KEY }}
          # Tùy chọn thêm
          SHOW_TITLE: true
          TIME_RANGE: "last_7_days"
          SHOW_TIME: true
          SHOW_TOTAL: true
          LANG_COUNT: 10
          BLOCKS: "░▒▓█"
