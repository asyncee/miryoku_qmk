tangle:
	rm -rf miryoku_babel
	emacs --batch -Q -L org-mode/lisp -f package-initialize -eval "(require 'ob-python)" -eval "(setq org-confirm-babel-evaluate nil)" -eval "(setq python-indent-guess-indent-offset-verbose nil)" ./readme.org -f org-babel-tangle
	mv tangled/qmk miryoku_babel
	rm -rf tangled

compile:
	qmk compile -c -kb crkbd -km manna-harbour_miryoku -e MIRYOKU_ALPHAS=QWERTY -e MIRYOKU_NAV=VI -e MIRYOKU_CLIPBOARD=MAC -e FORCE_LAYOUT=split_3x6_3

all: tangle compile
