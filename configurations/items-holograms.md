---
description: config_holo.yml
---

# ℹ Items Holograms

{% hint style="info" %}
This config allows you to:

* show **holograms **on dropped items (item name)
* **merge **dropped items **above **the **64 stack **limit, to avoid lag
* **merge **dropped **unstackable items **(on the ground)
* glow the **items **to make them more recognizable by players
{% endhint %}

(Description of the option is in gray)

```yaml
# language of the holograms (items names). folder: "lang"
lang: "en_us"
enabled: true
#which worlds do you want these options to be applied
worlds:
  - world
  - world_nether
  - world_the_end
merge:
  # merge dropped items even if their stack limit is exceeded (64+)
  force_merge:
    enabled: true
    radius: 7
    # please enable it only if you have duplication problems or incompatibility
    # with holograms plugins. For example with holograms of Shops plugin.
    # this option can increase CPU usage.
    more_precise_item_similarity_check__ENABLE_ONLY_IF_ANY_DUPE_PROBLEM: false
    max_stack:
      # max amount of stacked items of the same type
      custom_amount: 512
  merge_only_player_drops: false
  hologram:
    enabled: true
    format: "&f{name} &bx{amount}"
    glow:
      enabled: true
      # color of the hologram: 
      # https://hub.spigotmc.org/javadocs/spigot/org/bukkit/ChatColor.html
      color: "AQUA"
      only_player_dropped_items: true
      only_current_player: true
  blacklist:
    - BEDROCK
pickup_delay:
  legit_stacks: 2
  unstackable_items_stacks: 2
```

### languages

Download more languages here: [http://matteodev.it/spigot/holodrops/assets/lang.zip](http://matteodev.it/spigot/holodrops/assets/lang.zip)

```bash
Afrikaans = af_za
اللغة العربية = ar_sa
Asturianu = ast_es
Azərbaycanca = az_az
Беларуская = be_by
Български = bg_bg
Brezhoneg = br_fr
Braobans = brb
Bosanski = bs_BA
Catala (Valencià) = ca-val_es
Català = ca_es
Čeština = cs_cz
Cymraeg = cy_gb
Dansk = da_dk
Österreichisches Deitsch = de_at
Schwiizerdutsch = de_ch
Deutsch = de_de
Ελληνικά = el_gr
Pirate Speak = en_7s
English (Australia) = en_au
Canadian English = en_ca
English (UK) = en_gb
New Zealand English = en_nz
ɥsᴉꞁᵷuƎ (ɯopᵷuᴉꞰ pǝʇᴉuՈ) = en_ud
English (US) = en_us
Shakespearean English = en_ws
Anglish = enp
Esperanto = eo_uy
Español (Argentina) = es_ar
Español = es_CL
Español (España) = es_es
Español (México) = es_mx
Español (Uruguay) = es_uy
Español (Venezuela) = es_ve
Eesti = et_ee
Euskara = eu_es
فارسی = fa_ir
Suomi = fi_fi
Filipino = fil_ph
Føroyskt = fo_fo
Français québécois = fr_ca
Français = fr_fr
Frysk = fy_nl
Gaeilge = ga_ie
Gàidhlig = gd_gb
Galego = gl_es
Gaelg = gv_im
ʻŌlelo Hawaiʻi = haw
עברית = he_il
हिन्दी = hi_in
Hrvatski = hr_hr
Magyar = hu_hu
Հայերեն = hy_am
Bahasa Indonesia = id_id
Igbo = ig_ng
Ido = io_en
Íslenska = is_is
Italiano = it_it
日本語 = ja_jp
la .lojban. = jbo
ქართული = ka_ge
Taqbaylit = kab_dz
ಕನ್ನಡ = kn_in
한국어 = ko_kr
Kölsch/Ripoarisch = ksh_de
Kernewek = kw_gb
Latina = la_va
Lëtzebuergesch = lb_lu
Limburgs = li_li
LOLCAT = lol_aa
Lietuvių = lt_lt
Latviešu = lv_lv
Te Reo Māori = mi_nz
Македонски = mk_mk
Монгол = mn_mn
Kanien’kéha = moh_us
Bahasa Melayu = ms_my
Malti = mt_mt
Norsk Bokmål = nb_no
Platdüütsk = nds_de
Vlaams = nl_be
Nederlands = nl_nl
Norsk Nynorsk = nn_no
Norsk Bokmål = no_no
Nuučaan̓uł = nuk
Occitan = oc_fr
Ojibwemowin = oj_ca
Övdalsk = ovd_se
Polski = pl_pl
Português (Brasil) = pt_br
Português (Portugal) = pt_pt
Quenya = qya_aa
Română = ro_ro
Русский = ru_ru
Slovenčina = sk_sk
Slovenščina = sl_si
Davvisámegiella = sme
Af-Soomaali = so_so
Shqip = sq_al
Српски = sr_sp
Svenska = sv_se
Oschdallgaierisch = swg
Säggs'sch = sxu
Ślōnskŏ gŏdka = szl
தமிழ் = ta_IN
ภาษาไทย = th_th
tlhIngan Hol = tlh_aa
Türkçe = tr_tr
Татарча = tt_ru
Talossan = tzl_tzl
Українська = uk_ua
Vèneto = vec_it
Tiếng Việt = vi_vn
Frängisch = vmf_de
Yorùbá = yo_ng
简体中文 - 中国 = zh_cn
繁體中文 - 台灣 = zh_tw
```
