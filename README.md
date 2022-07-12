[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![JCS-ELPA](https://raw.githubusercontent.com/jcs-emacs/badges/master/elpa/v/sideline-lsp.svg)](https://jcs-emacs.github.io/jcs-elpa/#/sideline-lsp)

# sideline-lsp
> Show lsp information with sideline

[![CI](https://github.com/emacs-sideline/sideline-flycheck/actions/workflows/test.yml/badge.svg)](https://github.com/emacs-sideline/sideline-flycheck/actions/workflows/test.yml)

*P.S. The implementation is extracted and modified from [lsp-ui-sideline](https://github.com/emacs-lsp/lsp-ui#lsp-ui-sideline)
's code action*.

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-refresh-toc -->
**Table of Contents**

- [sideline-lsp](#sideline-lsp)
    - [🔨 Quickstart](#🔨-quickstart)
    - [🔧 Customization](#🔧-customization)
        - [🧪 Variables](#🧪-variables)
        - [🧪 Face](#🧪-face)
    - [💥 Replace `lsp-ui-sideline`](#💥-replace-lsp-ui-sideline)
    - [Contribute](#contribute)

<!-- markdown-toc end -->

## 🔨 Quickstart

```elisp
(leaf sideline
  :init
  (setq sideline-backends-right '(sideline-lsp)))
  
(leaf lsp-mode :hook (lsp-mode-hook . sideline-mode))  ; enable it when lsp is on
(leaf lsp-ui :init (setq lsp-ui-sideline-enable nil))  ; disable original sideline
```

## 🔧 Customization

#### 🧪 Variables

* `sideline-lsp-update-mode` - When set to 'line' the information will be updated
when user changes current line otherwise the information will be updated when
user changes current point
* `sideline-lsp-ignore-duplicate` - Ignore duplicate code actions
* `sideline-lsp-code-actions-prefix` - Prefix to insert before the code action title.

#### 🧪 Face

* `sideline-lsp-code-action` - Face used to highlight code action text.

## 💥 Replace `lsp-ui-sideline`

```elisp
(setq lsp-ui-sideline-enable nil)  ; disable lsp-ui-sideline
```

Customize backends according to your options:

* `lsp-ui-sideline-show-code-actions` - add `sideline-lsp`
* `lsp-ui-sideline-show-diagnostics` - add `sideline-flycheck`

Hence, you should

```elisp
(setq sideline-backends-right '(sideline-lsp sideline-flycheck))
```

## Contribute

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Elisp styleguide](https://img.shields.io/badge/elisp-style%20guide-purple)](https://github.com/bbatsov/emacs-lisp-style-guide)
[![Donate on paypal](https://img.shields.io/badge/paypal-donate-1?logo=paypal&color=blue)](https://www.paypal.me/jcs090218)

If you would like to contribute to this project, you may either
clone and make pull requests to this repository. Or you can
clone the project and establish your own branch of this tool.
Any methods are welcome!
