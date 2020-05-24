<p align="center">
  <img src="https://github.com/inokufu/api/blob/master/source/images/logo_inokufu_API_cloud_square.svg" alt="Inokufu API Cloud Documentation " width="300">
  <br>
</p>

<p align="center">Inokufu API Cloud helps you supercharge your app with the best learning data.</p>




Features
------------

* **Clean, intuitive design** — With Slate, the description of your API is on the left side of your documentation, and all the code examples are on the right side. Inspired by [Stripe's](https://stripe.com/docs/api) and [PayPal's](https://developer.paypal.com/webapps/developer/docs/api/) API docs. Slate is responsive, so it looks great on tablets, phones, and even in print.

* **Everything on a single page** — Gone are the days when your users had to search through a million pages to find what they wanted. Slate puts the entire documentation on a single page. We haven't sacrificed linkability, though. As you scroll, your browser's hash will update to the nearest header, so linking to a particular point in the documentation is still natural and easy.

* **Slate is just Markdown** — When you write docs with Slate, you're just writing Markdown, which makes it simple to edit and understand. Everything is written in Markdown — even the code samples are just Markdown code blocks.

* **Write code samples in multiple languages** — If your API has bindings in multiple programming languages, you can easily put in tabs to switch between them. In your document, you'll distinguish different languages by specifying the language name at the top of each code block, just like with GitHub Flavored Markdown.

* **Out-of-the-box syntax highlighting** for [over 100 languages](https://github.com/jneen/rouge/wiki/List-of-supported-languages-and-lexers), no configuration required.

* **Automatic, smoothly scrolling table of contents** on the far left of the page. As you scroll, it displays your current position in the document. It's fast, too. We're using Slate at TripIt to build documentation for our new API, where our table of contents has over 180 entries. We've made sure that the performance remains excellent, even for larger documents.

* **Let your users update your documentation for you** — By default, your Slate-generated documentation is hosted in a public GitHub repository. Not only does this mean you get free hosting for your docs with GitHub Pages, but it also makes it simple for other developers to make pull requests to your docs if they find typos or other problems. Of course, if you don't want to use GitHub, you're also welcome to host your docs elsewhere.

* **RTL Support** Full right-to-left layout for RTL languages such as Arabic, Persian (Farsi), Hebrew etc.

Getting started with Slate is super easy! Simply press the green "use this template" button above and follow the instructions below. Or, if you'd like to check out what Slate is capable of, take a look at the [sample docs](https://slatedocs.github.io/slate/).

Getting Started with Slate
------------------------------

### Prerequisites

You're going to need:

 - **Linux or macOS** — Windows may work, but is unsupported.
 - **Ruby, version 2.3.1 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

### Getting Set Up

1. Press the green "use this template" button at the top of this page.
2. Follow the instructions to create a new copy of the Slate repository.
3. Clone your repository (not our original one) to your hard drive with `git clone https://github.com/YOURUSERNAME/slate.git`
4. `cd slate`
5. Initialize and start Slate. You can either do this locally, or with Vagrant:

```shell
# either run this to run locally
bundle install
bundle exec middleman server

# OR run this to run with vagrant
vagrant up

# OR run this to run with docker
docker build . -t slate:latest # this only needs to be run once
docker run -p 4567:4567 -v $(pwd)/source:/srv/slate/source slate:latest
```

You can now see the docs at http://localhost:4567. Whoa! That was fast!

Now that Slate is all set up on your machine, you'll probably want to learn more about [editing Slate markdown](https://github.com/slatedocs/slate/wiki/Markdown-Syntax), or [how to publish your docs](https://github.com/slatedocs/slate/wiki/Deploying-Slate).

### Note on JavaScript Runtime

For those who don't have JavaScript runtime or are experiencing JavaScript runtime issues with ExecJS, it is recommended to add the [rubyracer gem](https://github.com/cowboyd/therubyracer) to your gemfile and run `bundle` again.

Questions? Need Help? Found a bug?
--------------------

If you've got questions about setup, deploying, special feature implementation in your fork, or just want to chat with the developer, please feel free to send us an email to [support@inokufu.com](mailto:support@inokufu.com)!


Credits
--------------------
This API documentation was created with Slate. Check it out at <a href="https://slatedocs.github.io/slate">slatedocs.github.io/slate</a>.
