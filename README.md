# The Manuscript: Transportome Profiler
To compile the manuscript, you will need a local installation of `texlive` and `biber`.
Biber should be packaged in most distros. You can google how to install it.
`texlive` is a bit harder.
For Arch users, follow the [archwiki article](https://wiki.archlinux.org/title/TeX_Live).
In general, the recommended way to install `texlive` is to follow the [official TeXlive guide](https://tug.org/texlive/quickinstall.html).

The instruction above are copied here, but you should check if they changed:
```bash
cd /tmp/
wget https://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz
zcat < install-tl-unx.tar.gz | tar xf -
cd install-tl-*
# Install only the medium image
perl ./install-tl --no-interaction --scheme=medium
```

You will probably need to install extra packages to compile successfully.
The command to do this for `tlmgr` is in `.../transportome_profiler/paper/install_pkgs.sh`:
```bash
sudo ./install_pkgs.sh
```
I am a weird man online. Suffice to say you should not `sudo` anything without inspecting it manually beforehand.

Once everything is installed, you should simply run `make paper`. `make` will run the analysis (to generate the figures for the manuscript), and then generate the paper itself. Keep reading if you want to *just* compile the manuscript, and not run the analysis proper.

## Just edit the manuscript
If you just want to edit the manuscript, but do not care about restarting the analysis, you can simply run `make thin_paper`. The paper will be built (with no figures) and saved to `/paper/src/main.pdf`. 

If you have access to pre-built images (from e.g. a previous run) you can just drop them in `/paper/src/resources/figures/generated` and even `make thin_paper` will pick them up and isert them in the output.

