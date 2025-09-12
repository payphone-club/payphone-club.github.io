# payphone-club.github.io

Our website, located at https://payphone.club

This site is built with the open-source [mkdocs](https://www.mkdocs.org/) static site generator, which converts Markdown pages into HTML. 

## Contributing

Anyone is welcome to submit updates to this site via [pull request](https://github.com/https://github.com/payphone-club/payphone-club.github.io/pulls).

GitHub maintains a [great guide for creating a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) if you've never made one before.

Note that if you are part of the Payphone.club organization you can make a pull request utilizing the [shared repository mode](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/getting-started/about-collaborative-development-models#shared-repository-model) which is easy, fast, and great for collaboration. If you are outside of the org you must [create a pull request from a fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork).

After submitting a PR, someone in the organization will review the changes and either approve them or request updates.

Merged updates will go live automatically via a GitHub Actions workflow.

Content on the Payphone.club website is written in Markdown, and a quick reference is available [here](https://www.markdownguide.org/tools/mkdocs/).

### New Page

Creating a new page is as easy as creating the markdown file in the appropriate directory where the page should live (please use lowercase filenames and dashes in place of spaces):

```
cd payphone-club.github.io/
nano docs/identification/my-new-page.md
```

Minimally, pages should have a title, a small summary, and then the content of the page:

```
# Title of the Page

This is a small summary of what this page is about.

---

All the interesting page content goes here!
```

You likely want to then link to your page from a parent page. In the same directory there should be a `README.md` file or in some cases an `index.md` file:

```
ls docs/identification/
my-new-page.md  README.md
```

In here, where it makes sense, you can add a markdown link:

```
[My New Page](my-new-page.md)
```

### Existing Page

Much like with creating a new page, exisiting pages are easily edited with a text editor of your choice:

```
cd payphone-club.github.io/
nano docs/identification/an-existing-page.md
```

### Using Images

Images live in the `docs/img` folder, preferably in a subfolder based on their page name. For example, if you were editing `docs/identification/my-new-page.md`, images for this page would live in `docs/img/identification/my-new-page/`.

Unfortunately, when images are referenced in the page markdown, they must be loaded with a **relative** path. For example, here is how you would include an image on `docs/identification/my-new-page.md` that lives in the `docs/img/identification/my-new-page/` directory:

```
![This is description text for the image, DO FILL THIS OUT AS IT IS ALSO USED AS ALT TEXT](../img/identification/my-new-page/my-picture.jpg){400}
```

Note here we are setting the width of the image to `400px`. For the sake of page load times, please consider how large your images are. If necessary, use a smaller image on the page and link to a full-size version.

## Running Locally

You may want to run the site locally to test your changes.

Install the prerequisites:

```
sudo apt-get update
sudo apt-get install python3 python3-pip
pip install mkdocs mkdocs-image-captions mkdocs-macros-plugin
```

Clone the repo and change to the directory:

```
git clone https://github.com/payphone-club/payphone-club.github.io.git
cd payphone-club.github.io/
```

Serve the site locally:

```
mkdocs serve
```

OR serve the site locally and bind to all network interfaces:

```
mkdocs serve --dev-addr=0.0.0.0:8000
```

Then the site can be loaded in your browser via `http://127.0.0.1:8000` on the same machine, or using the local IP address on the same port if you wish to access it from another machine on the same network. Make sure the machine you are serving it on will let access in via the firewall!
