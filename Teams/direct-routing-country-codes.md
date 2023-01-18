---
title: Codici paese routing diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leggere questo articolo per individuare i codici paese del percorso multimediale per direct routing, in modo da poter selezionare il percorso multimediale ottimale.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a70dad128987a5fb0df639984be07b623f9ff425
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812673"
---
# <a name="direct-routing-media-path-country-codes"></a>Direct Routing media path country codes

Quando si sceglie un percorso di routing per i file multimediali, per impostazione predefinita l'instradamento diretto assegna sempre un data center in base all'indirizzo IP pubblico del controller dei confini della sessione (SBC) e seleziona sempre il percorso più vicino al data center SBC.

Tuttavia, in alcuni casi il percorso multimediale predefinito potrebbe non essere il percorso multimediale ottimale; Ad esempio, un indirizzo IP pubblico di un intervallo di Stati Uniti potrebbe essere assegnato a un indirizzo SBC situato in Europa. 

Usando il parametro -MediaRelayRoutingLocationOverride con i cmdlet New-CsOnlinePSTNGateway e Set-CsOnlinePSTNGateway, è possibile specificare l'area preferita per il traffico multimediale. Ad esempio, il comando seguente specifica che l'area preferita è Germania:

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

Si noti che Microsoft consiglia di impostare questo parametro solo se i registri chiamate indicano chiaramente che l'assegnazione predefinita del data center per il percorso multimediale non usa il percorso più vicino al data center SBC. 
 
## <a name="country-code-reference-table"></a>Tabella di riferimento del codice paese

La tabella seguente mostra i valori del codice paese per il parametro -MediaRelayRoutingLocationOverride:

| Paese         | Codice 
|-----------------|--------------------|
| Afghanistan     | AF |
| Isole Aland   | AX |
| Albania         | AL |
| Algeria         | DZ |
| Samoa americane  | COME |
| Andorra         | ANNUNCIO |
| Angola          | AO |
| Anguilla        | AI |
| Antartide      | AQ | 
| Antigua e Barbuda | AG |
| Argentina       | AR |
| Armenia         | AM |
| Aruba           | AW |
| Australia       | AU |
| Austria         | A |
| Azerbaigian      | AZ |
| Bahamas         | B |
| Bahrein         | BH |
| Bangladesh      | BD |
| Barbados        | BB |
| Bielorussia         | BY |
| Belgio         | BVE |
| Belize          | BZ |
| Benin           | BJ |
| Bermuda         | BM |
| Bhutan          | BT |
| Bolivia         | BO |
| Bonaire         | BQ |
| Bosnia ed Erzegovina | BA |
| Botswana        | BW |
| Isola Bouvet   | BV |
| Brasile          | BR |
| Territorio britannico dell'Oceano Indiano | I/O |
| Isole Vergini Britanniche | VG |
| Brunei          | BN |
| Bulgaria        | BG |
| Burkina Faso    | BF |
| Burundi         | BI |
| Cabo Verde      | CV |
| Cambogia        | KH |
| Camerun        | CM |
| Canada          | CA |
| Isole Cayman  | KY |
| Repubblica Centrafricana | CFR |
| Ciad            | TD |
| Cile           | CL |
| Cina           | CN |
| Isola Christmas | CX |
| Isole Cocos (Keeling) | CC |
| Colombia        | CO |
| Comore         | KM |
| Congo           | CG |
| Congo (RDC)     | CD |
| Isole Cook    | CK |
| Costa Rica      | CR |
| Costa d'Avorio   | CI |
| Croazia         | Risorse umane |
| Cuba            | CU |
| Curacao         | CW |
| Cipro          | CY |
| Cechia         | CZ |
| Danimarca         | DK |
| Gibuti        | DJ |
| Dominica        | DM |
| Repubblica Dominicana | FARE |
| Ecuador         | EC |
| Egitto           | EG |
| El Salvador     | SV |
| Guinea Equatoriale | GQ |
| Eritrea         | ER |
| Estonia         | EE |
| Eswatini        | SZ |
| Etiopia        | ET |
| Isole Falkland | FK |
| Isole Fær Øer   | FO |
| Figi            | FJ |
| Finlandia         | FI |
| Francia          | FR |
| Guyana francese   | MOROSA |
| Polinesia francese | PF |
| Terre australi francesi | TF |
| Gabon           | GA |
| Gambia          | GM |
| Georgia         | GE |
| Germania         | DE |
| Ghana           | GH |
| Gibilterra       | GI |
| Grecia          | GR |
| Groenlandia       | GL |
| Grenada         | GD |
| Guadalupa      | GP |
| Guam            | GU |
| Guatemala       | GT |
| Guernsey        | GG |
| Guinea          | GN |
| Guinea-Bissau   | GW |
| Guyana          | GY |
| Haiti           | CIAO |
| Heard e McDonald | HM |
| Honduras        | HN |
| RAS di Hong Kong   | HK |
| Ungheria         | HU |
| Islanda         | È |
| India           | POLLICI |
| Indonesia       | ID |
| Iran            | IR |
| Iraq            | IQ |
| Irlanda         | IE |
| Isola di Man     | Messaggistica istantanea |
| Israele          | IL |
| Italia           | IT |
| Giamaica         | JM |
| Jan Mayen       | XJ |
| Giappone           | JP |
| Jersey          | JE |
| Giordania          | JO |
| Kazakistan      | KZ |
| Kenya           | KE |
| Kiribati        | KI |
| Corea           | KR |
| Kosovo          | XK |
| Kuwait          | KW |
| Kirghizistan      | KG |
| Laos            | LA |
| Lettonia          | LV |
| Libano         | LB |
| Lesotho         | LS |
| Liberia         | LR |
| Libia           | LY |
| Liechtenstein   | LI |
| Lituania       | TENENTE |
| Lussemburgo      | LU |
| Macao - R.A.S.       | MO |
| Madagascar      | MG |
| Malawi          | MW |
| Malaysia        | MY |
| Maldive        | MV |
| Mali            | ML |
| Malta           | MONTE |
| Isole Marshall | MH |
| Martinica      | MQ |
| Mauritania      | SIGNOR |
| Mauritius       | MU |
| Mayotte         | YT |
| Messico          | MX |
| Micronesia      | FM |
| Moldova         | MD |
| Monaco          | MC |
| Mongolia        | MN |
| Montenegro      | ME |
| Montserrat      | SIGNORA |
| Marocco         | MA |
| Mozambico      | MZ |
| Myanmar         | MM |
| Namibia         | NA |
| Nauru           | NR |
| Nepal           | NP |
| Paesi Bassi     | NL |
| Nuova Caledonia   | NC |
| Nuova Zelanda     | NZ |
| Nicaragua       | NI |
| Niger           | NE |
| Nigeria         | NG |
| Niue            | NU |
| Isola Norfolk  | NF |
| Corea del Nord     | KP |
| Macedonia del Nord | MK |
| Isole Marianne settentrionali | NP |
| Norvegia          | NO |
| Oman            | OM |
| Pakistan        | PK |
| Palau           | PW |
| Autorità Palestinese | PS |
| Panamá          | PA |
| Papua Nuova Guinea | PG |
| Paraguay        | PY |
| Perù            | PE |
| Filippine     | PH |
| Isole Pitcairn | PN |
| Polonia          | PL |
| Portogallo        | PT |
| Portorico     | PR |
| Qatar           | QA |
| Riunione         | RE |
| Romania         | RO |
| Russia          | RU |
| Ruanda          | RW |
| Saba            | XS |
| Saint Barthélemy | BEATO |
| Saint Kitts e Nevis | KN |
| Saint Lucia     | LC |
| Saint Martin    | MF |
| Saint-Pierre e Miquelon | PM |
| Saint Vincent e Grenadine | VC |
| Samoa           | WS |
| San Marino      | SM |
| Sao Tome e Principe | SAN |
| Arabia Saudita    | SA |
| Senegal         | SN |
| Serbia          | RS |
| Seychelles      | M.B |
| Sierra Leone    | SL | 
| Singapore       | SG |
| Sint Eustatius  | XE |
| Sint Maarten    | SX |
| Slovacchia        | SK |
| Slovenia        | SL |
| Isole Salomone | SB |
| Somalia         | COSÌ |
| Sudafrica    | Immagine dell'icona |
| Georgia del Sud e Sandwich Australi | GS |
| Sud Sudan     | SS |
| Spagna           | ES |
| Sri Lanka       | LK |
| Sant'Elena, Ascensione, Tristan da Cunha | SH |
| Sudan           | SD |
| Suriname        | SUOR |
| Svalbard        | SJ |
| Svezia          | SE |
| Svizzera     | CH |
| Siria           | SY |
| Taiwan          | TW |
| Tagikistan      | TJ |
| Tanzania        | TZ |
| Thailandia        | TH |
| Timor-Leste     | TL |
| Togo            | TG |
| Tokelau         | TK |
| Tonga           | A |
| Trinidad e Tobago | TT |
| Tunisia         | TN |
| Turchia          | TR |
| Turkmenistan    | TM |
| Isole Turks e Caicos | TC |
| Tuvalu          | TV |
| Isole americane più remote | Messaggistica unificata |
| Isole Vergini Americane | VI |
| Uganda          | UG |
| Ucraina         | UA |
| Emirati Arabi Uniti | AE |
| Regno Unito  | GB |
| Stati Uniti   | NOI |
| Uruguay         | UY |
| Uzbekistan      | UZ |
| Vanuatu         | VU |
| Città del Vaticano    | VIRGINIA |
| Venezuela       | VE |
| Vietnam         | VN |
| Wallis e Futuna | WF |
| Yemen           | VOI |
| Zambia          | ZM |
| Zimbabwe        | ZW |
