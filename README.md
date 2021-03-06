<p align="center">
    <a href="https://semgrep.dev"><img src="semgrep.svg" height="150" alt="Semgrep logo"/></a>
</p>
<h3 align="center">
  Lightweight static analysis for many languages.
  </br>
  Find bugs and enforce code standards.
</h3>
<p align="center">
  <a href="https://formulae.brew.sh/formula/semgrep">
    <img src="https://img.shields.io/homebrew/v/semgrep?style=flat-square" alt="Homebrew" />
  </a>
  <a href="https://pypi.org/project/semgrep/">
    <img alt="PyPI" src="https://img.shields.io/pypi/v/semgrep?style=flat-square&color=blue">
  </a>
  <a href="https://r2c.dev/slack">
    <img src="https://img.shields.io/badge/slack-join-green?style=flat-square" alt="Issues welcome!" />
  </a>
  <a href="https://github.com/returntocorp/semgrep/issues/new/choose">
    <img src="https://img.shields.io/badge/issues-welcome-green?style=flat-square" alt="Issues welcome!" />
  </a>
  <a href="https://github.com/returntocorp/semgrep#readme">
    <img src="https://img.shields.io/github/stars/returntocorp/semgrep?label=GitHub%20Stars&style=flat-square" alt="1500+ GitHub stars" />
  </a>
  <a href="https://twitter.com/intent/follow?screen_name=r2cdev">
    <img src="https://img.shields.io/twitter/follow/r2cdev?label=Follow%20r2cdev&style=social&color=blue" alt="Follow @r2cdev" />
  </a>
</p>
</br>

Semgrep is a fast, open-source, static analysis tool that excels at expressing code standards — without complicated queries — and surfacing bugs early at editor, commit, and CI time. Precise rules look like the code you’re searching; no more traversing abstract syntax trees or wrestling with regexes.

The [Semgrep Registry](https://semgrep.dev/explore) has 900+ rules written by the Semgrep community covering security, correctness, and performance bugs. No need to DIY unless you want to.

Semgrep runs offline, on uncompiled code.

Semgrep is used in production everywhere from one-person startups to multi-billion dollar companies; it is the engine inside tools like [NodeJsScan](https://semgrep.dev/p/nodejsscan). Semgrep is developed and commercially supported by [r2c, a software security company](https://r2c.dev). r2c’s free hosted service, [Semgrep Community](https://semgrep.dev), lets organizations write and share rules, and manage Semgrep in CI across many projects. r2c also offers a paid hosted tier for enterprises, [Semgrep Team](https://r2c.dev/pricing).

### Language support


<h4 align="center">General availability</h4>
<p align="center">
Go · Java · JavaScript · JSON · Python</br>
</p>
<h4 align="center">Beta</h4>
<p align="center">
Ruby · TypeScript · JSX · TSX</br></br>
Visit <a href="https://semgrep.dev/docs/status/">Supported languages</a> for the complete list.
</p>

### Getting started

To install Semgrep use Homebrew or pip, or run without installation via Docker:

```sh
# For macOS
$ brew install semgrep

# For Ubuntu/WSL/Linux/macOS
$ python3 -m pip install semgrep

# To try Semgrep without installation run via Docker
$ docker run --rm -v "${PWD}:/src" returntocorp/semgrep --help
```

Once installed, Semgrep can run with single rules or entire rulesets. Visit [Running rules](running-rules.md) to learn more or try the following:

```sh
# Check for Python == where the left and right hand sides are the same (often a bug)
$ semgrep -e '$X == $X' --lang=py path/to/src

# Run the r2c-ci ruleset (with rules for many languages) on your own code!
$ semgrep --config=p/r2c-ci path/to/src
```

Visit [Getting started](https://semgrep.dev/docs/getting-started/) to learn more.

### Rule examples

Visit [Rule examples](https://semgrep.dev/docs/writing-rules/rule-ideas/) for use cases and ideas.

| Use case                          | Semgrep rule                                                                                                                                                                                                                                                                                                                                           |
| :-------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ban dangerous APIs                | [Prevent use of exec](https://semgrep.dev/s/clintgibler:no-exec)                                                                                                                                                                                                                                                                                         |
| Search routes and authentication   | [Extract Spring routes](https://semgrep.dev/s/clintgibler:spring-routes)                                                                                                                                                                                                                                                                                 |
| Enforce the use secure defaults   | [Securely set Flask cookies](https://semgrep.dev/s/dlukeomalley:flask-set-cookie)                                                                                                                                                                                                                                                                        |
| Enforce project best-practices    | [Use assertEqual for == checks](https://semgrep.dev/s/dlukeomalley:use-assertEqual-for-equality), [Always check subprocess calls](https://semgrep.dev/s/dlukeomalley:unchecked-subprocess-call)                                                                                                                                                            |
| Codify project-specific knowledge | [Verify transactions before making them](https://semgrep.dev/s/dlukeomalley:verify-before-make)                                                                                                                                                                                                                                                          |
| Audit security hotspots           | [Finding XSS in Apache Airflow](https://semgrep.dev/s/ievans:airflow-xss), [Hardcoded credentials](https://semgrep.dev/s/dlukeomalley:hardcoded-credentials)                                                                                                                                                                                               |
| Audit configuration files         | [Find S3 ARN uses](https://semgrep.dev/s/dlukeomalley:s3-arn-use)                                                                                                                                                                                                                                                                                        |
| Migrate from deprecated APIs      | [DES is deprecated](https://semgrep.dev/editor?registry=java.lang.security.audit.crypto.des-is-deprecated), [Deprecated Flask APIs](https://semgrep.dev/editor?registry=python.flask.maintainability.deprecated.deprecated-apis), [Deprecated Bokeh APIs](https://semgrep.dev/editor?registry=python.bokeh.maintainability.deprecated.deprecated_apis) |
| Apply automatic fixes             | [Use listenAndServeTLS](https://semgrep.dev/s/clintgibler:use-listenAndServeTLS)   


### Integrations

Visit [Integrations](https://semgrep.dev/docs/integrations/) to learn about Semgrep editor, commit, and CI integrations.

### FAQ

Visit [FAQ](https://semgrep.dev/docs/faq/) to learn more. Semgrep is supported by [r2c](https://r2c.dev).

### Contributing

Visit [Contributing](https://semgrep.dev/docs/contributing/) or join the [r2c Community Slack](https://r2c.dev/slack) to learn more. Semgrep is LGPL-2.1 licensed. 

### Usage

Visit [CLI Usage](https://semgrep.dev/docs/cli-usage/) for usage and exit code documentation.

### Upgrading

To upgrade, run the command below associated with how you installed Semgrep:

```sh
# Using Homebrew
$ brew upgrade semgrep

# Using pip
$ python3 -m pip install --upgrade semgrep

# Using Docker
$ docker pull returntocorp/semgrep:latest
```
