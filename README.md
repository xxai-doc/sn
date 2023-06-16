<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Inokurudzirwa kuisa nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) kutanga, uye ipapo `direnv allow` mushure mekupinda mudhairekitori ( [the .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) ichaitwa otomatiki mushure mekupinda mudhairekitori).

Zvazvinoreva ndezvi: Kushandura kweChinese kuJapan, Korean, Chirungu, Chirungu, kushandura kune mimwe mitauro yose. Kana iwe chete uchida kutsigira chiChinese neChirungu, unogona kungonyora `zh: en` .

## kumberi-kuguma kodhi

* [kumberi-kuguma kodhi](https://github.com/xxai-art/web)
* [Mutauro mapaketi esaiti yakazara](https://github.com/xxai-art/web/tree/main/i18n)
* [Mutauro mapaketi ekupinda mamodule](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Webhusaiti Multilingual Documentation](https://github.com/xxai-doc)

Mutauro wepurogiramu yekumberi ndeye [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , iyo inowedzera zvimwe zvinhu zvichienderana nekofiscript syntax, ona [./coffee_plus.md](./coffee_plus.md) .

## Internationalization yemawebhusaiti uye zvinyorwa

Vaka pazvirongwa zvitatu zvinotevera

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Chivakashure chinoti `.mdt` , unogona kushandisa sintakisi yakafanana neiyi `<+ ./coffee_plus/import.js>` kureva mafaera ekunze, uye gadzira chiratidzo nechivakashure `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Shanduro yeMarkdown haishandure macode nemalink, uye inochengeta mitsara yakaturikirwa. Kana shanduro ikagadziridzwa asi zvinyorwa zvepakutanga zvikasavandudzwa, kuishandura zvakare hakuzopedzi gadziridzo yeshanduro yacho.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Mafaira emutauro ekushandura mawebhusaiti akagadzirwa `yaml` .

### Document Translation Automation Mirayiridzo

Ona kodhi repository [xxai-art/doc](https://github.com/xxai-art/doc)

Inokurudzirwa kuisa nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) kutanga, uye ipapo `direnv allow` mushure mekupinda mudhairekitori ( [the .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) ichaitwa otomatiki mushure mekupinda mudhairekitori).

Kuti ndidzivise iyo hombe kodhi base yakashandurirwa mumazana emitauro, ndakagadzira yakaparadzana kodhi base yemutauro wega wega uye ndakagadzira sangano rekuchengetedza kodhi base.

Kuseta shanduko yemamiriro ekunze `GITHUB_ACCESS_TOKEN` wobva wamhanya [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) zvinozogadzira iyo kodhi repository.

Zvechokwadi, iwe unogonawo kuiisa mukodhi yekodhi.

Referensi yemanyorero [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Iyo script code inodudzirwa seizvi:

[bunx](https://bun.sh/docs/cli/bunx) inotsiva npx, inokurumidza. Ehe, kana iwe usina bun yakaiswa, unogona kushandisa `npx` pachinzvimbo.

`bunx mdt zh` renders `.mdt` mu zh directory as `.md` , ona 2 mafaera akabatanidzwa pazasi

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` ndiyo musimboti kodhi yekushandura (kana uine `nodejs` chete yakaiswa, asi `bun` uye `direnv` zvisina kuiswa, unogona zvakare kumhanya `npx i18n` kushandura).

Ichaparura [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , kugadziridzwa `i18n.yml` mugwaro iri kunotevera:

```
en:
zh: ja ko en
```

Zvazvinoreva ndezvi: Kushandura kweChinese kuJapan, Korean, Chirungu, Chirungu, kushandura kune mimwe mitauro yose. Kana iwe chete uchida kutsigira chiChinese neChirungu, unogona kungonyora `zh: en` .

Yekupedzisira ndeye [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , inobvisa zviri pakati pemusoro wemusoro uye yekutanga subtitle yemutauro wega wega `README.md` kuti ibude `README.md` . Iyo kodhi iri nyore kwazvo, unogona kuzvitarisa iwe pachako.

Google API inoshandiswa kushandura mahara. Kana usingakwanise kupinda paGoogle, gadzirisa uye kuseta mumiriri, senge:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Manyorero eshanduro achaburitsa cache yakaturikirwa mu `.i18n` dhairekitori, ndapota itarise iine `git status` woiwedzera kucode repository kuti udzivise kudzokororwa shanduro.

Ndokumbira umhanye `bunx i18n` pese paunogadzirisa shanduro kuti uvandudze cache.

Kana zvinyorwa zvepakutanga uye shanduro yakashandurwa panguva imwe chete, cache ichavhiringidzika, saka kana iwe uchida kugadzirisa, unogona kungogadzirisa imwe chete, uye wobva wamhanya `bunx i18n` kuti uvandudze cache.
