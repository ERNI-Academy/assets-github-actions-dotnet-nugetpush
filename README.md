# About assets-github-actions-dotnet-nugetpush

Is a github composite action to push nugets for dotnet projects

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
<!-- ALL-CONTRIBUTORS-BADGE:END -->

## Built With

This section should list any major frameworks that you built your project using. Leave any add-ons/plugins for the acknowledgements section. Here are a few examples.

- [Composite action](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action)

## Features

- push nugets for dotnet projects

## Getting Started

Check the releases of https://github.com/ERNI-Academy/assets-github-actions-dotnet-nugetpush/releases
Find the lastest tag or one of the previus versions e.g. "v1"
Then your able to use it in your workflows

Please take a look at https://docs.github.com/en/actions/creating-actions/creating-a-composite-action to see how composite actions works.

## Prerequisites

You would need to have a Package Token for github with **write:packages** and **read:packages** scopes.
Follow this link https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token to see how to create a PAT.

Remember that Package Token is sensitive and should be keeped as a secret. 

## Installation

In the workflow of your target dotnet repository do this:

1. Your workflow:

```yml
name: NuGet

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

 #maybe other steps of your desire

     # insert this in order to have nuget push:
     - id: nuget-push
       uses: ERNI-Academy/assets-github-actions-dotnet-nugetpush@v1  # this is name of the action plus the version "v1" find the lastest tag in the releases
       with:
         pakages_token: '[your package token]'         # your package token, we recommend that to storage the token in a secret and use it like ${{ secrets.PACKAGE_TOKEN }}         
```

## Contributing

Please see our [Contribution Guide](CONTRIBUTING.md) to learn how to contribute.

## License

![MIT](https://img.shields.io/badge/License-MIT-blue.svg)

(LICENSE) © 2022 [ERNI - Swiss Software Engineering](https://www.betterask.erni)

## Code of conduct

Please see our [Code of Conduct](CODE_OF_CONDUCT.md)

## Stats

Check [https://repobeats.axiom.co/](https://repobeats.axiom.co/) for the right URL

## Follow us

[![Twitter Follow](https://img.shields.io/twitter/follow/ERNI?style=social)](https://www.twitter.com/ERNI)
[![Twitch Status](https://img.shields.io/twitch/status/erni_academy?label=Twitch%20Erni%20Academy&style=social)](https://www.twitch.tv/erni_academy)
[![YouTube Channel Views](https://img.shields.io/youtube/channel/views/UCkdDcxjml85-Ydn7Dc577WQ?label=Youtube%20Erni%20Academy&style=social)](https://www.youtube.com/channel/UCkdDcxjml85-Ydn7Dc577WQ)
[![Linkedin](https://img.shields.io/badge/linkedin-31k-green?style=social&logo=Linkedin)](https://www.linkedin.com/company/erni)

## Contact

📧 [esp-services@betterask.erni](mailto:esp-services@betterask.erni)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- ALL-CONTRIBUTORS-LIST:END -->
This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
