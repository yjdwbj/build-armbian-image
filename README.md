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
- Smoke tests starts after **repository update** is done succesfully.
- Nightly images are build once per day, at 5:00 AM UTC, or if [build config is changed](https://github.com/armbian/os/blob/main/userpatches/targets-release-nightly.yaml)
- Manually, when Armbian [release manager](https://github.com/orgs/armbian/teams/release-manager) executes a build action

# Latest smoke tests results:

- installs kernels, dtb and headers that are defined and supported by the board
- runs network and computing performance tests (7z benchmark)
- store armbianmonitor logs

<!--START_SECTION:data-section-->
<table width="100%"><tr><td align="left"><a href=""><b>Board name</b></a></td><td align="left"><b>Started</b></td><td align=right><b>Kernel version</b></td><td align=right><b>Iperf</b></td><td align=right><b>7z -b</b></td></tr><tr><td align="left"><a href="https://paste.armbian.com/kebexivono">Orange Pi Win</a></td><td align="left">2023-08-20&nbsp;09:01:55</td><td align=right>5.15.93-sunxi64</td><td align=right>770</td><td align=right>2528</td></tr><tr><td align="left"><a href="https://paste.armbian.com/ohatutaxil">Orange Pi Win</a></td><td align="left">2023-08-20&nbsp;09:17:01</td><td align=right>6.4.10-edge-sunxi64</td><td align=right>889</td><td align=right>2785</td></tr><tr><td align="left"><a href="https://paste.armbian.com/utitesurik">Espressobin</a></td><td align="left">2023-08-20&nbsp;09:10:42</td><td align=right>5.15.93-mvebu64</td><td align=right>800</td><td align=right>1022</td></tr><tr><td align="left"><a href="https://paste.armbian.com/gafafalula">Espressobin</a></td><td align="left">2023-08-20&nbsp;09:31:28</td><td align=right>6.1.46-edge-mvebu64</td><td align=right>840</td><td align=right>1023</td></tr><tr><td align="left"><a href="https://paste.armbian.com/igotupojes">Pine H64</a></td><td align="left">2023-08-20&nbsp;08:57:57</td><td align=right>5.15.93-sunxi64</td><td align=right>882</td><td align=right>3759</td></tr><tr><td align="left"><a href="https://paste.armbian.com/poxupujira">Pine H64</a></td><td align="left">2023-08-20&nbsp;09:07:18</td><td align=right>6.4.10-edge-sunxi64</td><td align=right>853</td><td align=right>3652</td></tr><tr><td align="left"><a href="https://paste.armbian.com/nepimazere">RockPro 64</a></td><td align="left">2023-08-20&nbsp;08:54:22</td><td align=right>5.15.93-rockchip64</td><td align=right>881</td><td align=right>6446</td></tr><tr><td align="left"><a href="https://paste.armbian.com/suferiwuye">RockPro 64</a></td><td align="left">2023-08-20&nbsp;09:01:12</td><td align=right>6.4.11-edge-rockchip64</td><td align=right>890</td><td align=right>6444</td></tr><tr><td align="left"><a href="https://paste.armbian.com/axoqabezen">Rockpi E</a></td><td align="left">2023-08-20&nbsp;09:01:47</td><td align=right>5.15.93-rockchip64</td><td align=right>87</td><td align=right>2950</td></tr><tr><td align="left"><a href="https://paste.armbian.com/nopirozilo">Rockpi E</a></td><td align="left">2023-08-20&nbsp;09:15:57</td><td align=right>6.4.11-edge-rockchip64</td><td align=right>90</td><td align=right>3272</td></tr><tr><td align="left"><a href="https://paste.armbian.com/gukukujili">NanoPi R6S</a></td><td align="left">2023-08-20&nbsp;08:51:39</td><td align=right>5.10.160-legacy-rk35xx</td><td align=right>880</td><td align=right>15936</td></tr><tr><td align="left"><a href="https://paste.armbian.com/cayiyegadi">Orange Pi 3 LTS</a></td><td align="left">2023-08-20&nbsp;08:57:42</td><td align=right>5.15.93-sunxi64</td><td align=right>798</td><td align=right>3910</td></tr><tr><td align="left"><a href="https://paste.armbian.com/wogerilaqe">Orange Pi 3 LTS</a></td><td align="left">2023-08-20&nbsp;09:07:04</td><td align=right>6.4.10-edge-sunxi64</td><td align=right>831</td><td align=right>3745</td></tr><tr><td align="left"><a href="https://paste.armbian.com/ovowipubot">Odroid C4</a></td><td align="left">2023-08-20&nbsp;08:55:50</td><td align=right>6.1.11-meson64</td><td align=right>881</td><td align=right>5547</td></tr><tr><td align="left"><a href="https://paste.armbian.com/afageriros">Odroid C4</a></td><td align="left">2023-08-20&nbsp;09:03:41</td><td align=right>6.4.11-edge-meson64</td><td align=right>870</td><td align=right>5598</td></tr><tr><td align="left"><a href="https://paste.armbian.com/lasokeneqa">Rockpi 4B</a></td><td align="left">2023-08-20&nbsp;08:54:56</td><td align=right>5.15.93-rockchip64</td><td align=right>880</td><td align=right>6296</td></tr><tr><td align="left"><a href="https://paste.armbian.com/wipifanigu">Rockpi 4B</a></td><td align="left">2023-08-20&nbsp;09:02:14</td><td align=right>6.4.11-edge-rockchip64</td><td align=right>880</td><td align=right>6104</td></tr><tr><td align="left"><a href="https://paste.armbian.com/ecaduveyot">NanoPi M4</a></td><td align="left">2023-08-20&nbsp;08:54:43</td><td align=right>5.15.93-rockchip64</td><td align=right>902</td><td align=right>6687</td></tr><tr><td align="left"><a href="https://paste.armbian.com/ifuxukebiz">NanoPi M4</a></td><td align="left">2023-08-20&nbsp;09:01:40</td><td align=right>6.4.11-edge-rockchip64</td><td align=right>890</td><td align=right>6620</td></tr><tr><td align="left"><a href="https://paste.armbian.com/zufoqucidu">Banana Pi Pro</a></td><td align="left">2023-08-20&nbsp;09:03:12</td><td align=right>5.15.93-sunxi</td><td align=right>292</td><td align=right>1025</td></tr><tr><td align="left"><a href="https://paste.armbian.com/enoripemet">Banana Pi Pro</a></td><td align="left">2023-08-20&nbsp;09:18:13</td><td align=right>6.4.10-edge-sunxi</td><td align=right>387</td><td align=right>1016</td></tr><tr><td align="left"><a href="https://paste.armbian.com/turuxoceto">Cubietruck</a></td><td align="left">2023-08-20&nbsp;09:10:14</td><td align=right>5.15.93-sunxi</td><td align=right>395</td><td align=right>1005</td></tr><tr><td align="left"><a href="https://paste.armbian.com/ecifixozex">Cubietruck</a></td><td align="left">2023-08-20&nbsp;09:30:43</td><td align=right>6.4.10-edge-sunxi</td><td align=right>352</td><td align=right>992</td></tr><tr><td align="left"><a href="https://paste.armbian.com/kuzihosada">NanoPi R4S</a></td><td align="left">2023-08-20&nbsp;08:56:44</td><td align=right>5.15.93-rockchip64</td><td align=right>850</td><td align=right>6462</td></tr><tr><td align="left"><a href="https://paste.armbian.com/esozixubiq">NanoPi R4S</a></td><td align="left">2023-08-20&nbsp;09:04:26</td><td align=right>6.4.11-edge-rockchip64</td><td align=right>871</td><td align=right>6418</td></tr><tr><td align="left"><a href="https://paste.armbian.com/noholabebi">Odroid N2</a></td><td align="left">2023-08-20&nbsp;08:53:08</td><td align=right>6.1.11-meson64</td><td align=right>890</td><td align=right>8766</td></tr><tr><td align="left"><a href="https://paste.armbian.com/igaziwodut">Odroid N2</a></td><td align="left">2023-08-20&nbsp;08:58:21</td><td align=right>6.4.11-edge-meson64</td><td align=right>889</td><td align=right>8792</td></tr><tr><td align="left"><a href="https://paste.armbian.com/zetuyomuka">Orange Pi 3</a></td><td align="left">2023-08-20&nbsp;08:55:16</td><td align=right>5.15.93-sunxi64</td><td align=right>870</td><td align=right>4214</td></tr><tr><td align="left"><a href="https://paste.armbian.com/cufitatimu">Orange Pi 3</a></td><td align="left">2023-08-20&nbsp;09:02:48</td><td align=right>6.4.10-edge-sunxi64</td><td align=right>859</td><td align=right>3954</td></tr><tr><td align="left"><a href="https://paste.armbian.com/asaqotilal">NanoPi Neo 3</a></td><td align="left">2023-08-20&nbsp;08:56:45</td><td align=right>5.15.93-rockchip64</td><td align=right>827</td><td align=right>3445</td></tr><tr><td align="left"><a href="https://paste.armbian.com/nogovabifo">NanoPi Neo 3</a></td><td align="left">2023-08-20&nbsp;09:06:01</td><td align=right>6.4.11-edge-rockchip64</td><td align=right>770</td><td align=right>2637</td></tr><tr><td align="left"><a href="https://paste.armbian.com/cefojokoma">Orange Pi Zero</a></td><td align="left">2023-08-20&nbsp;08:59:07</td><td align=right>5.15.126-legacy-sunxi</td><td align=right>89</td><td align=right>2011</td></tr><tr><td align="left"><a href="https://paste.armbian.com/yuzehafevo">Orange Pi Zero</a></td><td align="left">2023-08-20&nbsp;09:14:20</td><td align=right>5.15.93-sunxi</td><td align=right>90</td><td align=right>1915</td></tr><tr><td align="left"><a href="https://paste.armbian.com/bapizasuco">Orange Pi Zero</a></td><td align="left">2023-08-20&nbsp;09:29:22</td><td align=right>6.4.10-edge-sunxi</td><td align=right>90</td><td align=right>2003</td></tr><tr><td align="left"><a href="https://paste.armbian.com/izadixuyar">Orange Pi Zero Plus</a></td><td align="left">2023-08-20&nbsp;09:02:39</td><td align=right>5.15.93-sunxi64</td><td align=right>830</td><td align=right>2463</td></tr><tr><td align="left"><a href="https://paste.armbian.com/rorujakiqe">Orange Pi Zero Plus</a></td><td align="left">2023-08-20&nbsp;09:16:49</td><td align=right>6.4.10-edge-sunxi64</td><td align=right>830</td><td align=right>2527</td></tr><tr><td align="left"><a href="https://paste.armbian.com/nulikabacu">Orange Pi Zero2</a></td><td align="left">2023-08-20&nbsp;09:06:12</td><td align=right>5.15.93-sunxi64</td><td align=right>672</td><td align=right>1177</td></tr><tr><td align="left"><a href="https://paste.armbian.com/nulikabacu">Orange Pi Zero2</a></td><td align="left">2023-08-20&nbsp;09:31:54</td><td align=right>5.15.93-sunxi64</td><td align=right>672</td><td align=right>1177</td></tr><tr><td align="left"><a href="https://paste.armbian.com/">Clearfog Pro</a></td><td align="left">2023-08-20&nbsp;08:55:52</td><td align=right>5.15.93-mvebu</td><td align=right>820</td><td align=right>2184</td></tr><tr><td align="left"><a href="https://paste.armbian.com/">Clearfog Pro</a></td><td align="left">2023-08-20&nbsp;09:03:43</td><td align=right>6.2.16-edge-mvebu</td><td align=right>788</td><td align=right>2182</td></tr><tr><td align="left"><a href="https://paste.armbian.com/ifinotoben">ODROID M1</a></td><td align="left">2023-08-20&nbsp;08:55:47</td><td align=right>6.3.13-edge-rk3568-odroid</td><td align=right>870</td><td align=right>5127</td></tr><tr><td align="left"><a href="https://paste.armbian.com/orayobizuc">Tinker Board 2</a></td><td align="left">2023-08-20&nbsp;08:55:59</td><td align=right>5.15.93-rockchip64</td><td align=right>840</td><td align=right>6840</td></tr><tr><td align="left"><a href="https://paste.armbian.com/uqaxotaxok">Tinker Board 2</a></td><td align="left">2023-08-20&nbsp;09:03:26</td><td align=right>6.4.11-edge-rockchip64</td><td align=right>880</td><td align=right>6775</td></tr><tr><td align="left"><a href="https://paste.armbian.com/ohebaroram">Orange Pi 4 LTS</a></td><td align="left">2023-08-20&nbsp;08:55:40</td><td align=right>5.15.93-rockchip64</td><td align=right>899</td><td align=right>5546</td></tr><tr><td align="left"><a href="https://paste.armbian.com/miwonecote">Orange Pi 4 LTS</a></td><td align="left">2023-08-20&nbsp;09:03:35</td><td align=right>6.4.11-edge-rockchip64</td><td align=right>880</td><td align=right>4506</td></tr><tr><td align="left"><a href="https://paste.armbian.com/remaraquce">Le potato</a></td><td align="left">2023-08-20&nbsp;09:01:42</td><td align=right>6.1.11-meson64</td><td align=right>93</td><td align=right>3733</td></tr><tr><td align="left"><a href="https://paste.armbian.com/oyaluroduj">Le potato</a></td><td align="left">2023-08-20&nbsp;09:15:07</td><td align=right>6.4.11-edge-meson64</td><td align=right>90</td><td align=right>3737</td></tr><tr><td align="left"><a href="n/a">BigTreeTech CB1</a></td><td align="left">2023-08-20&nbsp;08:47:37</td><td align=right>n/a</td><td align=right>n/a</td><td align=right>n/a</td></tr><tr><td align="left"><a href="https://paste.armbian.com/owixikokal">Banana Pi M5</a></td><td align="left">2023-08-20&nbsp;08:53:48</td><td align=right>6.1.11-meson64</td><td align=right>790</td><td align=right>5526</td></tr><tr><td align="left"><a href="https://paste.armbian.com/cekasowuku">Banana Pi M5</a></td><td align="left">2023-08-20&nbsp;08:59:43</td><td align=right>6.4.11-edge-meson64</td><td align=right>890</td><td align=right>5579</td></tr><tr><td align="left"><a href="https://paste.armbian.com/oxevuzezik">Khadas VIM2</a></td><td align="left">2023-08-20&nbsp;08:58:55</td><td align=right>6.1.11-meson64</td><td align=right>889</td><td align=right>5981</td></tr><tr><td align="left"><a href="https://paste.armbian.com/iwakoseyoj">Khadas VIM2</a></td><td align="left">2023-08-20&nbsp;09:10:01</td><td align=right>6.4.11-edge-meson64</td><td align=right>828</td><td align=right>6051</td></tr><tr><td align="left"><a href="https://paste.armbian.com/aqifevizuf">Khadas VIM1</a></td><td align="left">2023-08-20&nbsp;08:57:27</td><td align=right>6.1.11-meson64</td><td align=right>93</td><td align=right>3670</td></tr><tr><td align="left"><a href="https://paste.armbian.com/wuletuhima">Khadas VIM1</a></td><td align="left">2023-08-20&nbsp;09:07:04</td><td align=right>6.4.11-edge-meson64</td><td align=right>90</td><td align=right>3676</td></tr><tr><td align="left"><a href="https://paste.armbian.com/axolixesad">Orange Pi R1 Plus LTS</a></td><td align="left">2023-08-20&nbsp;09:03:26</td><td align=right>5.15.93-rockchip64</td><td align=right>493</td><td align=right>1957</td></tr><tr><td align="left"><a href="https://paste.armbian.com/ihucemezic">Orange Pi R1 Plus LTS</a></td><td align="left">2023-08-20&nbsp;09:19:35</td><td align=right>6.4.11-edge-rockchip64</td><td align=right>480</td><td align=right>1775</td></tr><tr><td align="left"><a href="n/a">Rock 5B</a></td><td align="left">2023-08-20&nbsp;08:48:12</td><td align=right>n/a</td><td align=right>n/a</td><td align=right>n/a</td></tr><tr><td align="left"><a href="https://paste.armbian.com/ewebuwixam">Orange Pi Zero Plus 2</a></td><td align="left">2023-08-20&nbsp;09:01:22</td><td align=right>5.15.93-sunxi</td><td align=right>32</td><td align=right>n/a</td></tr></table>
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

## OS download

- [Download](https://www.armbian.com/download/)

## Support

- [Using Armbian](https://forum.armbian.com/forum/23-using-armbian/)

## Contact

- [Forums](https://forum.armbian.com) for Participate in Armbian
- IRC: `#armbian` on Libera.chat
- Discord: [https://discord.gg/armbian](https://discord.gg/armbian)
- Follow [@armbian](https://twitter.com/armbian) on Twitter, [Fosstodon](https://fosstodon.org/@armbian) or [LinkedIn](https://www.linkedin.com/company/armbian).
- Bugs: [issues](https://github.com/armbian/build/issues) / [JIRA](https://armbian.atlassian.net/jira/dashboards/10000)
- Office hours: [Wednesday, 12 midday, 18 afternoon, CET](https://calendly.com/armbian/office-hours)

## License

This software is published under the GPL-2.0 License license.
