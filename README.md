Skip to content
Search or jump to…
Pull requests
Issues
Codespaces
Marketplace
Explore
 
@mennasaad1 
anuraghazra
/
anuraghazra
Public
Fork your own copy of anuraghazra/anuraghazra
Code
Issues
39
Pull requests
4
Actions
Projects
Security
Insights
anuraghazra/.github/workflows/peerlist.yml
@anuraghazra
anuraghazra Update peerlist.yml
Latest commit 2b90b1f on Nov 24, 2021
 History
 1 contributor
42 lines (42 sloc)  1.4 KB

name: 'peerlist-demo'
on:
  workflow_dispatch:
    inputs:
      username:
        required: true
        description: 'Peerlist username'
      card_size:
        description: 'Card size (sm, md, lg) or any number'
        default: 'lg'
      theme_name:
        description: 'Theme name'
        default: 'default'
      text_color:
        description: 'Text color'
      title_color:
        description: 'Title color'
      bg_color:
        description: 'Background color'
      output_path:
        default: 'images/peerlist-profile.png'
        description: 'Output path to upload the image'
      branch:
        default: 'master'
        description: 'Branch which you want to upload the image, change it depending on your main branch'
jobs:
  peerlist-run:
    name: Generate peerlist overview
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: browser-actions/setup-chrome@latest
      - uses: 'anuraghazra/peerlist-profile-action@main'
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          username: ${{github.event.inputs.username}}
          theme_name: ${{github.event.inputs.theme_name}}
          card_size: ${{github.event.inputs.card_size}}
          title_color: ${{github.event.inputs.title_color}}
          text_color: ${{github.event.inputs.text_color}}
          bg_color: ${{github.event.inputs.bg_color}}
          branch: ${{github.event.inputs.branch}}
Footer
© 2023 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
anuraghazra/peerlist.yml at 6e732d92945015e74a55de65dd5f517c0f1077ec · anuraghazra/anuraghazra
