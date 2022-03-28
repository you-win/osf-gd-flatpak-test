# osf-gd-flatpak-test

## Dev instructions
1. Follow the `flatpak-builder` setup instructions
2. Install the appropriate sdks and version (21.08)
3. Create a venv to hold local Python packages
4. Pip install `requirements-parser`
5. Pip install the OpenSeeFace dependencies into the venv [from here](https://github.com/you-win/openseeface-gd/blob/master/resources/scripts/create_venv.sh)
6. Generate a `requirements.txt` based off of that
7. Run `python flatpak-pip-generator --requirements-file requirements.txt` to generate a requirements file in the same directory

## Build instructions
1. Download the latest release from [openseeface-gd](https://github.com/you-win/openseeface-gd/releases)
2. Extract everything into a directory called `openseeface-gd`. Make sure the files are not nested inside of another folder (e.g. `openseeface-gd/OpenSeeFaceGD/<file>` is wrong. It should be `openseeface-gd/<file>`)
3. Run `flatpak-builder build-dir org.youwin.openseefacegd.yml`. This will start building everything
4. Observe that building packages occurs and eventually fails :)

## Things still broken
1. The pip generator is unable to grab onnxruntime for some reason
2. Building fails it looks like wheel files were pulled for python and those files have other build dependencies
