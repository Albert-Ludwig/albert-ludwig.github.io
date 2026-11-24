# Haoran Ji · Academic website

Personal academic website for Haoran Ji, a Mechatronics Engineering undergraduate at McMaster University. The site uses [Academic Pages](https://github.com/academicpages/academicpages.github.io) and Jekyll.

**Website** [albert-ludwig.github.io](https://albert-ludwig.github.io)

## Edit the site

| Location | Contents |
| --- | --- |
| `_config.yml` | Site identity, repository, author profile, and optional media |
| `_data/navigation.yml` | Main navigation |
| `_data/research_interests.yml` | Research interests shown on About and Research |
| `_pages/` | About, Research, Publications, Projects, CV, and the 404 page |
| `_publications/` | Manuscript and publication records |
| `_portfolio/` | Project profiles and research experiences |
| `_sass/layout/_academic-profile.scss` | Typography, layout, responsive navigation, and color styles |
| `.github/workflows/jekyll.yml` | GitHub Pages build and deployment |

For manuscripts under review, set `review_status: Under review` and provide the submission venue. Add publication dates and citation details only once they are confirmed.

### Add media

- **Photograph** — Put the image in `images/` and set `author.avatar` to its filename.
- **CV PDF** — Put the PDF in `files/` and set `media.cv_pdf` to its site-relative path.
- **Research figures** — Put the images in `images/research/` and add each figure's path and descriptive alternative text to `media.research_figures`. A caption is optional.
- **Project videos** — Put web-ready videos in `files/videos/` and add their title and path to `media.project_videos`. Optional fields support a poster image and an English WebVTT caption track.
- **Public email** — Set `author.email` to add an email link in the footer.

This example adds a CV, a research figure, and a project video.

```yaml
media:
  cv_pdf: /files/haoran-ji-cv.pdf
  research_figures:
    - path: /images/research/field-reconstruction.png
      alt: "Map showing the reconstructed environmental field"
      caption: "Gaussian Process field reconstruction"
  project_videos:
    - title: Clearpath Jackal navigation demo
      path: /files/videos/jackal-demo.mp4
      poster: /images/research/jackal-demo.jpg
      captions: /files/videos/jackal-demo.vtt
```

## Build locally

Use Ruby 3.3 with Bundler.

```sh
bundle install
bundle exec jekyll serve
```

Open [localhost:4000](http://localhost:4000). Use this command to reproduce the production build.

```sh
JEKYLL_ENV=production bundle exec jekyll build --strict_front_matter
```

## Deploy with GitHub Pages

1. Use the `main` branch of [Albert-Ludwig/albert-ludwig.github.io](https://github.com/Albert-Ludwig/albert-ludwig.github.io).
2. In the repository's **Settings → Pages**, select **GitHub Actions** under **Build and deployment → Source**. A repository administrator or maintainer can set the source. See [GitHub's publishing source documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).
3. Push to `main`, or use **Actions → Deploy academic website → Run workflow**. The workflow builds Jekyll and deploys the artifact to the `github-pages` environment.

The workflow uses the repository's built-in `GITHUB_TOKEN`. GitHub Actions must be enabled, and the `github-pages` environment must allow deployments from `main`. The deploy job requests `pages: write` and `id-token: write`. See [GitHub's custom Pages workflow documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages).
