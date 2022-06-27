**English** | [中文](README-zh.md)

<h1 align="center">RemoteMC-Docs</h1>

<p align="center"> 
  <b>User and Dev documentations of RemoteMC Series</b>
</p>

<p align="center">
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/License-CC--BY--NC--SA--4.0-important?style=for-the-badge" />
  </a>
</p>

## Guide to contribute to the documentation

**Your commit messages should follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) guidelines**.

### Install the requirements

``` bash
pip3 install -r requirements.txt
```

### Build the documentation (convert Sphinx rst/md to html)

(This step is only for preview the edited files)

``` bash
make clean
make html
```

The documentation will be generated in `docs/html` directory in `zh_CN` (Simplified Chinese).

If you need to change the language of the generated documentation, you can modify the `zh_CN` of `language = os.environ.get('READTHEDOCS_LANGUAGE', 'zh_CN')` of line 69 of `source/conf.py` file to your designated language.

### Update the translation files

(This step uses Simplified Chinese as an example, if you need to use other languages, replace `zh_CN` with your designated language)

``` bash

``` bash
cd source
sphinx-build -b gettext . _locale
sphinx-intl update -p _locale -l zh_CN
```

This step will generate some `.po` files in `source/_locale/zh_CN` directory, which will be used to store the translation content:

- Empty translations will be generated for new content.
- `#, fuzzy` comments will be added to the translation for changed texts. Update the translation and remove the `#, fuzzy` comment.
- Translations for removed texts will be moved to the bottom of the `.po` file and be commented out, you should remove them.

## 📜 License

> **RemoteMC-Docs is licensed under [CC-BY-NC-SA-4.0 License](LICENSE).**

``` text
RemoteMC-Docs (c) by iXOR Techbology, Cubik65536, and contributors.

RemoteMC-Docs is licensed under a
Creative Commons Attribution-NonCommercial 4.0 International License.

You should have received a copy of the license along with this
work. If not, see <http://creativecommons.org/licenses/by-nc/4.0/>.
```
