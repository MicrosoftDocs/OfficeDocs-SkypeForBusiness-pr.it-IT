---
title: Codici paese routing diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leggere questo articolo per individuare i codici paese del percorso multimediale per Direct Routing, in modo da poter selezionare il percorso multimediale ottimale.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 330d178c7bfa969020ffc8c26b1e05283c182ae8
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717997"
---
# <a name="direct-routing-media-path-country-codes"></a>Codici del paese del percorso multimediale per il routing diretto

Quando si sceglie un percorso di routing per i supporti multimediali, per impostazione predefinita, Il routing diretto assegna sempre un data center in base all'indirizzo IP pubblico del session border controller (SBC) e seleziona sempre il percorso più vicino al data center SBC.

Tuttavia, in alcuni casi il percorso multimediale predefinito potrebbe non essere quello ottimale. ad esempio, a un indirizzo IP pubblico di un intervallo degli Stati Uniti potrebbe essere assegnato un indirizzo SBC situato in Europa. 

Usando il parametro -MediaRelayRoutingLocationOverride con i cmdlet New-CsOnlinePSTNGateway e Set-CsOnlinePSTNGateway, è possibile specificare l'area preferita per il traffico multimediale. Ad esempio, il comando seguente specifica che l'area preferita è la Germania:

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

Si noti che Microsoft consiglia di impostare questo parametro solo se i registri delle chiamate indicano chiaramente che l'assegnazione predefinita del data center per il percorso multimediale non usa il percorso più vicino al data center SBC. 

> [!NOTE]
> Il parametro MediaRelayRoutingLocationOverride è riservato per l'uso con i gestori gestiti.
 
## <a name="country-code-reference-table"></a>Tabella di riferimento del codice paese

La tabella seguente mostra i valori dei codici paese per il parametro -MediaRelayRoutingLocationOverride:

| Paese         | Codice 
|-----------------|--------------------|
| Afghanistan     | AF |
| Isole Aland   | AX |
| Albania         | AL |
| Algeria         | DZ |
| Samoa americane  | AS |
| Andorra         | Active Directory |
| Angola          | AO |
| Anguilla        | Intelligenza artificiale |
| Antartide      | AQ | 
| Antigua e Barbuda | Gruppo di disponibilità |
| Argentina       | AR |
| Armenia         | AM |
| Aruba           | AW |
| Australia       | AU |
| Austria         | AT |
| Azerbaigian      | AZ |
| Bahamas         | BS |
| Bahrein         | BH |
| Bangladesh      | BD |
| Barbados        | BB |
| Bielorussia         | BY |
| Belgio         | BE |
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
| Burundi         | Business intelligence |
| Cabo Verde      | CV |
| Cambogia        | KH |
| Camerun        | CM |
| Canada          | CA |
| Isole Cayman  | KY |
| Repubblica Centrafricana | CF |
| Ciad            | TD |
| Cile           | CL |
| Cina           | CN |
| Isola di Natale | CX |
| Isole Cocos (Keeling) | CC |
| Colombia        | CO |
| Comore         | KM |
| Congo           | CG |
| Congo (RDC)     | CD |
| Isole Cook    | CK |
| Costa Rica      | CR |
| Cote d'Ivoire   | CI |
| Croazia         | Risorse umane |
| Cuba            | CU |
| Curacao         | CW |
| Cipro          | CY |
| Cecoslovacchia         | CZ |
| Danimarca         | DK |
| Gibuti        | DJ |
| Dominica        | DM |
| Repubblica Dominicana | DO |
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
| Guyana francese   | GF |
| Polinesia francese | PF |
| Territori meridionali francesi | TF |
| Gabon           | Ga |
| Gambia          | GM |
| Georgia         | GE |
| Germania         | DE |
| Ghana           | GH |
| Gibilterra       | GI |
| Grecia          | GR |
| Groenlandia       | Contabilità generale |
| Grenada         | GD |
| Guadalupa      | Criteri di gruppo |
| Guam            | GU |
| Guatemala       | GT |
| Guernsey        | GG |
| Guinea          | GN |
| Guinea-Bissau   | GW |
| Guyana          | GY |
| Haiti           | HI |
| Isole Heard e McDonald | HM |
| Honduras        | HN |
| RAS di Hong Kong   | HK |
| Ungheria         | HU |
| Islanda         | IS |
| India           | IN |
| Indonesia       | ID |
| Iran            | A/A |
| Iraq            | QI |
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
| Lettonia          | VL |
| Libano         | LB |
| Lesotho         | LS |
| Liberia         | LR |
| Libia           | LY |
| Liechtenstein   | LI |
| Lituania       | LT |
| Lussemburgo      | LU |
| Macao SAR       | MO |
| Madagascar      | MG |
| Malawi          | MW |
| Malaysia        | MY |
| Maldive        | MV |
| Mali            | ML |
| Malta           | MT |
| Isole Marshall | MH |
| Martinica      | MQ |
| Mauritania      | MR |
| Mauritius       | MU |
| Mayotte         | YT |
| Messico          | MX |
| Micronesia      | FM |
| Moldova         | MD |
| Monaco          | MC |
| Mongolia        | MN |
| Montenegro      | ME |
| Montserrat      | MS |
| Marocco         | Ma |
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
| Isola norfolk  | NF |
| Corea del Nord     | KP |
| Macedonia del Nord | MK |
| Isole Marianne settentrionali | NP |
| Norvegia          | No |
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
| Saint Barthélemy | BL |
| Saint Kitts e Nevis | KN |
| Saint Lucia     | LC |
| Saint Martin    | MF |
| Saint Pierre e Miquelon | PM |
| Saint Vincent e Grenadine | VC |
| Samoa           | WS |
| San Marino      | SM |
| Sao Tome e Principe | ST |
| Arabia Saudita    | SA |
| Senegal         | SN |
| Serbia          | RS |
| Seychelles      | SC |
| Sierra Leone    | SL | 
| Singapore       | SG |
| Sint Eustatius  | XE |
| Sint Maarten    | SX |
| Slovacchia        | SK |
| Slovenia        | SL |
| Isole Salomone | SB |
| Somalia         | Allora |
| Sudafrica    | Immagine dell'icona |
| Georgia del Sud e Isole Sandwich del Sud | GS |
| Sud Sudan     | SS |
| Spagna           | ES |
| Sri Lanka       | LK |
| Sant'Elena, Ascensione, Tristan da Cunha | SH |
| Sudan           | SD |
| Suriname        | SR |
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
| U.S. Outlying Islands | Messaggistica unificata |
| Isole Vergini Americane | VI |
| Uganda          | UG |
| Ucraina         | UA |
| Emirati Arabi Uniti | AE |
| Regno Unito  | GB |
| Stati Uniti   | Stati Uniti |
| Uruguay         | UY |
| Uzbekistan      | UZ |
| Vanuatu         | VU |
| Città del Vaticano    | VA |
| Venezuela       | VE |
| Vietnam         | VN |
| Wallis e Futuna | WF |
| Yemen           | YE |
| Zambia          | ZM |
| Zimbabwe        | ZW |
