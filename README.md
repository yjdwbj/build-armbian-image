<p align="center">
  <a href="#build-framework">
   <img src="https://raw.githubusercontent.com/armbian/build/master/.github/armbian-logo.png" alt="Armbian logo" width="144">
  </a><br>
  <strong>Armbian OS</strong><br>
<br>
<a href=https://github.com/armbian/os/actions/workflows/complete-artifact-matrix-all.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/complete-artifact-matrix-all.yml?logo=githubactions&label=Artifacts%20make&style=for-the-badge&branch=main"></a>
<a href=https://github.com/armbian/os/actions/workflows/repository-update.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/repository-update.yml?logo=githubactions&label=Repository%20update&style=for-the-badge&branch=main"></a>
<a href=https://github.com/armbian/os#latest-smoke-tests-results><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/smoke-tests.yml?logo=githubactions&label=Smoke%20tests&style=for-the-badge&branch=main"></a>
</p>


# What does this project do?

- Keeps build framework [packages artifacts](https://github.com/orgs/armbian/packages) cache up to date
- Keeps stable [apt.armbian.com](https://apt.armbian.com) and nightly [beta.armbian.com](https://beta.armbian.com) packages repository up to date
- Builds [nightly](https://github.com/armbian/os/releases) and [stable images](https://www.armbian.com/download/) and uploads them to Armbian CDN
- Keep synchronizing the selection of [3rd party](external) applications with Armbian repositories
- Tests install of all packages added onto stable and testing Debian and Ubuntu releases

# How to enable images?

If you want to enable build configurations, edit [yaml config files](userpatches) and send a pull request. ([example](https://github.com/armbian/os/commit/70f3be4f3d96e9a301be751d3ecf3a24394356f9) )

# When is this happening?

- Artifacts cache is updated every eight hours, starting at 0:00 AM UTC
- Repository update starts after **artifacts cache update** is done succesfully.
- Smoke tests starts **manually**.
- Nightly images are build once per day, at 2:00 AM UTC, or if [build config is changed](https://github.com/armbian/os/blob/main/userpatches/targets-release-nightly.yaml)
- Manually, when Armbian [release manager](https://github.com/orgs/armbian/teams/release-manager) executes a build action

# Latest smoke tests results:

- installs **kernels**, **device tree blob** and **headers**
- runs **network** (iperf) and **computing performance** tests (7z benchmark)
- store **armbianmonitor** logs

<!--START_SECTION:data-section-->
<table width="100%"><tr><td align="left"><a id=Board ID href=#Board ID><b>Board name</b></a></td><td align=center><b>Kernel version</b></td><td align=center><b>Support</b></td><td align=left><b>Logs</b></td><td align=right><b>Iperf</b></td><td align=right><b>7z -b</b></td><td align=right><b>Repo</b></td></tr><tr><td align="left"><a id=orangepi-r1 href=#orangepi-r1>Orange Pi R1</a></td><td align=center>6.1.68-current-sunxi</td><td align=center><a href=#orangepi-r1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/iqezixekaf><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>2762</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi-r1 href=#orangepi-r1>Orange Pi R1</a></td><td align=center>6.6.7-edge-sunxi</td><td align=center><a href=#orangepi-r1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/opetacugun><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>2235</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=#khadas-vim1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/rinapacowu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>3705</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=#khadas-vim1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/olizijiyok><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>3711</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.1.68-current-sunxi64</td><td align=center><a href=#orangepizeroplus><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/iqafasoyev><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>840</td><td align=right>2593</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.6.7-edge-sunxi64</td><td align=center><a href=#orangepizeroplus><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/icosoholes><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>840</td><td align=right>2688</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.1.68-current-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/figocesida><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>840</td><td align=right>4333</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.6.7-edge-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/oqixoguwid><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>878</td><td align=right>4265</td><td align=right>beta</td></tr><tr><td align="left"><a id=zeropi href=#zeropi>ZeroPi</a></td><td align=center>5.15.143-legacy-sunxi</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/kefiqineco><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>556</td><td align=right>2693</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepiplus2e href=#orangepiplus2e>Orange Pi+ 2E</a></td><td align=center>5.15.143-legacy-sunxi</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/cidaxoxaki><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>818</td><td align=right>2151</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2ultra href=#bananapim2ultra>Banana Pi M2 Ultra</a></td><td align=center>6.1.68-current-sunxi</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/xigofeloye><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>851</td><td align=right>2711</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=#bananapim2pro><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/gasupiziya><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>5503</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=#bananapim2pro><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/eyubopisaj><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>5469</td><td align=right>beta</td></tr><tr><td align="left"><a id=tinkerboard-2 href=#tinkerboard-2>Tinker Board 2</a></td><td align=center>6.1.68-current-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/febehopawe><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>930</td><td align=right>6856</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=#lepotato><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/tanijokacu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>3778</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=#lepotato><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/nagimomayu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>3785</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi3 href=#orangepi3>Orange Pi 3</a></td><td align=center>6.1.68-current-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/uvuvuyodij><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>4346</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi3 href=#orangepi3>Orange Pi 3</a></td><td align=center>6.6.7-edge-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/usuvenunac><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>950</td><td align=right>4158</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=#orangepi5><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/totohakuvi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>932</td><td align=right>15655</td><td align=right>beta</td></tr><tr><td align="left"><a id=tinkerboard href=#tinkerboard>Tinker Board</a></td><td align=center>6.1.68-current-rockchip</td><td align=center><a href=#tinkerboard><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/zogecafewi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5062</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=center>6.1.68-current-sunxi</td><td align=center><a href=#orangepizero><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/gelehohaqo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>91</td><td align=right>2314</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=#khadas-vim2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/afucifoqeg><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>6210</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=#khadas-vim2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/egotedaqut><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>887</td><td align=right>6079</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=center>6.1.68-current-sunxi64</td><td align=center><a href=#orangepizero2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/lodiqojuci><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>827</td><td align=right>3139</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=center>6.6.7-edge-sunxi64</td><td align=center><a href=#orangepizero2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/metizokuti><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>827</td><td align=right>2963</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=#khadas-vim3><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/iyocuxukeb><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>930</td><td align=right>9559</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=#khadas-vim3><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/gugizolowo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>910</td><td align=right>9673</td><td align=right>beta</td></tr><tr><td align="left"><a id=tanix-tx6 href=#tanix-tx6>Tanix TX6</a></td><td align=center>6.1.68-current-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/akajixuvew><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>4323</td><td align=right>beta</td></tr><tr><td align="left"><a id=tanix-tx6 href=#tanix-tx6>Tanix TX6</a></td><td align=center>6.6.7-edge-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/capugiyobe><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>4244</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepioneplus href=#orangepioneplus>Orange Pi One+</a></td><td align=center>6.1.68-current-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/jazotemona><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>4325</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>6.1.68-current-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ojekinexav><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>850</td><td align=right>6602</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>6.6.7-edge-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/mosupuwobe><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>960</td><td align=right>6770</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim4 href=#khadas-vim4>Khadas VIM4</a></td><td align=center>5.4.180-legacy-meson-s4t7</td><td align=center><a href=#khadas-vim4><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/aneyesatag><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>920</td><td align=right>7972</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=#bananapim5><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/eyehenunis><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>5494</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=#bananapim5><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ojojonivos><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>881</td><td align=right>5526</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>n/a</td><td align=center><a href=#uefi-x86><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>n/a</td><td align=center><a href=#uefi-x86><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>n/a</td><td align=center><a href=#uefi-x86><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopineo3 href=#nanopineo3>NanoPi Neo 3</a></td><td align=center>6.1.68-current-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/zijevetibe><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>864</td><td align=right>3315</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpro64 href=#rockpro64>RockPro 64</a></td><td align=center>n/a</td><td align=center><a href=#rockpro64><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/edecavotut><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>5612</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/deqexohoju><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>5652</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=#odroidc2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/okaroxefok><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>749</td><td align=right>3984</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=#odroidc2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/aqeboyujad><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>4055</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.1.68-current-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/enuyadibuz><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>2674</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.7.0-rc6-edge-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ecisodunam><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>2617</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5-plus href=#orangepi5-plus>Orange Pi 5 Plus</a></td><td align=center>6.7.0-rc4-edge-rockchip-rk3588</td><td align=center><a href=#orangepi5-plus><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uhawuxagib><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>15280</td><td align=right>beta</td></tr><tr><td align="left"><a id=bigtreetech-cb1 href=#bigtreetech-cb1>BigTreeTech CB1</a></td><td align=center>6.1.43-legacy-sun50iw9-btt</td><td align=center><a href=#bigtreetech-cb1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/gihifolexo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>2678</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi-r1plus-lts href=#orangepi-r1plus-lts>Orange Pi R1 Plus LTS</a></td><td align=center>6.1.68-current-rockchip64</td><td align=center><a href=#orangepi-r1plus-lts><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/equnitekow><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>480</td><td align=right>1907</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/tovuyojube><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>8975</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/viqeguxece><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>935</td><td align=right>8895</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r1 href=#nanopi-r1>NanoPi R1</a></td><td align=center>n/a</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopi-r2s href=#nanopi-r2s>Nanopi R2S</a></td><td align=center>6.1.68-current-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/xeqaziwafo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>830</td><td align=right>3443</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r2s href=#nanopi-r2s>Nanopi R2S</a></td><td align=center>6.6.7-edge-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/oxirisuwuh><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>3351</td><td align=right>beta</td></tr><tr><td align="left"><a id=jetson-nano href=#jetson-nano>Jetson Nano</a></td><td align=center>6.1.68-current-arm64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/laqabihavu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>879</td><td align=right>3787</td><td align=right>beta</td></tr><tr><td align="left"><a id=jetson-nano href=#jetson-nano>Jetson Nano</a></td><td align=center>6.6.7-edge-arm64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/asipupagos><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>888</td><td align=right>3688</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=#bananapicm4io><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/utitilizar><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>9498</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=#bananapicm4io><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/zalaludote><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>850</td><td align=right>9291</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.4-edge-rk3568-odroid</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Staging&color=orange></a></td><td align=left><a href=https://paste.armbian.com/><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>610</td><td align=right>5232</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.4-edge-rk3568-odroid</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Staging&color=orange></a></td><td align=left><a href=https://paste.armbian.com/><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>670</td><td align=right>5303</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.1.68-current-rockchip64</td><td align=center><a href=#nanopi-r4s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/qilacolate><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>6470</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.6.7-edge-rockchip64</td><td align=center><a href=#nanopi-r4s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/bukafiziza><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>980</td><td align=right>6470</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.1.68-current-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/upeyibawos><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>861</td><td align=right>5794</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.7.0-rc6-edge-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/fenaqupahe><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>5750</td><td align=right>beta</td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=center>6.1.68-current-imx6</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/mevazaravi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>319</td><td align=right>2362</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1s href=#khadas-vim1s>Khadas VIM1S</a></td><td align=center>n/a</td><td align=center><a href=#khadas-vim1s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=#nanopi-r6s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/udibuqekeq><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>2249</td><td align=right>15773</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=#nanopi-r6s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/udibuqekeq><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>2249</td><td align=right>15773</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>5.15.143-legacy-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ratekulamu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>43</td><td align=right>4115</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.1.68-current-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ovebukoqax><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>50</td><td align=right>4023</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.6.7-edge-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/dogujadoga><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>40</td><td align=right>3910</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus2-h3 href=#orangepizeroplus2-h3>Orange Pi Zero Plus 2</a></td><td align=center>6.1.68-current-sunxi</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/sopefexagu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>34</td><td align=right>2659</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus2-h3 href=#orangepizeroplus2-h3>Orange Pi Zero Plus 2</a></td><td align=center>6.6.7-edge-sunxi</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/iguxuxayul><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>37</td><td align=right>2633</td><td align=right>beta</td></tr></table>
<!--END_SECTION:data-section-->

## Would you like to join spare hardware to this automated testings?

All you need to do is:

- deploy any latest Armbian image to hardware
- provide IP address
- [contact us](https://www.armbian.com/contact/)

Device has to be always on and easily accesible for you to re-image in case of failed upgrade.

## Development

- [Pull request](https://github.com/armbian/build/pulls)
- [Weekly developers meetings](https://forum.armbian.com/events/)
- [Forums for developers](https://forum.armbian.com/forum/4-advanced-users-development/)

## Download prebuilt images

- [quarterly released **supported** builds](https://www.armbian.com/download/?device_support=Standard%20support)
- [quarterly released **community maintained** builds](https://www.armbian.com/download/?device_support=Community%20maintained)
- [automatic released **rolling release** builds](https://github.com/armbian/os/releases/latest) (daily or when code changes)

## Support

- [Using Armbian](https://forum.armbian.com/forum/23-using-armbian/)

## Contact

- [Forums](https://forum.armbian.com) for Participate in Armbian
- IRC: `#armbian` on Libera.chat
- Discord: [https://discord.gg/armbian](https://discord.gg/armbian)
- Follow [@armbian](https://twitter.com/armbian) on X (formerly known as Twitter), [Fosstodon](https://fosstodon.org/@armbian) or [LinkedIn](https://www.linkedin.com/company/armbian).
- Bugs: [issues](https://github.com/armbian/build/issues) / [JIRA](https://armbian.atlassian.net/jira/dashboards/10000)
- Office hours: [Wednesday, 12 midday, 18 afternoon, CET](https://calendly.com/armbian/office-hours)
