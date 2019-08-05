---
title: Codici paese di routing diretto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Leggere questo articolo per individuare i codici paese dei percorsi multimediali per il routing diretto.
ms.openlocfilehash: 8ab2a6b9dbcbb676362c9fc7e39637aff0724a53
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36184588"
---
# <a name="direct-routing-media-path-country-codes"></a>Codice paese percorso diretto di routing multimediale

Quando si sceglie un percorso di routing per l'elemento multimediale, il routing diretto, per impostazione predefinita, assegna sempre un Data Center basato sull'indirizzo IP pubblico del SBC (Session Border Controller) e seleziona sempre il percorso più vicino al Data Center SBC.

Tuttavia, in alcuni casi il percorso multimediale predefinito potrebbe non essere il percorso multimediale ottimale; ad esempio, un IP pubblico di un intervallo degli Stati Uniti può essere assegnato a un SBC situato in Europa. 

Usando il parametro-MediaRelayRoutingLocationOverride con i cmdlet New-CsOnlinePSTNGateway e set-CsOnlinePSTNGateway, puoi specificare l'area preferita per il traffico multimediale. Ad esempio, il comando seguente specifica che l'area preferita è la Germania:

Set-CSOnlinePSTNGateway-Identity sbc1.contoso.com-MediaRelayRoutingLocationOverride DE 

Tieni presente che Microsoft consiglia di impostare questo parametro solo se i registri delle chiamate indicano chiaramente che l'assegnazione predefinita del Data Center per il percorso multimediale non usa il percorso più vicino al Data Center SBC. 
 
## <a name="country-code-reference-table"></a>Tabella di riferimento per il codice paese

La tabella seguente mostra i valori del codice paese per il parametro-MediaRelayRoutingLocationOverride:

| Paese         | Codice 
|-----------------|--------------------|
| Afghanistan     | AF |
| Isole Aland   | AX |
| Albania         | AL |
| Algeria         | DZ |
| Samoa americane  | COME |
| Andorra         | AD |
| Angola          | AO |
| Anguilla        | AL |
| Antartide      | SCHERMATA | 
| Antigua e Barbuda | AG |
| Argentina       | AR |
| Armenia         | SONO |
| Aruba           | AW |
| Australia       | AU |
| Austria         | A |
| Azerbaijan (Azərbaycan)      | AZ |
| Bahamas         | BS |
| Bahrein         | BH |
| Bangladesh      | BD |
| Barbados        | BB |
| Bielorussia         | BY |
| Belgio         | ESSERE |
| Belize          | BZ |
| Benin           | BJ |
| Bermuda         | BM |
| Bhutan          | BT |
| Bolivia         | BO |
| Bonaire         | BQ |
| Bosnia and Herzegovina (Bosna i Hercegovina) | BA |
| Botswana        | BW |
| Isola di Bouvet   | BV |
| Brasile          | BR |
| Territorio britannico dell'oceano indiano | IO |
| Isole Vergini britanniche | VG |
| Brunei          | BN |
| Bulgaria        | BG |
| Burkina Faso    | BF |
| Burundi         | BI |
| Cabo verde      | CV |
| Cambogia        | KH |
| Camerun        | CM |
| Canada          | CA |
| Cayman Islands  | KY |
| Repubblica Centrafricana | CF |
| Ciad            | TD |
| Cile           | CL |
| Cina           | CN |
| Isola di Natale | CX |
| Isole Cocos (Keeling) | CC |
| Colombia        | CO |
| Comoro         | KM |
| Congo           | CG |
| Congo (RDC)     | CD |
| Isole Cook    | NTO |
| Costa Rica      | CR |
| Costa d'Avorio   | CI |
| Croazia         | HR |
| Cuba            | CU |
| Curacao         | CW |
| Cipro          | CY |
| Cechia         | CZ |
| Danimarca         | DK |
| Gibuti        | DJ |
| Dominica        | DM |
| Repubblica dominicana | ESEGUIRE |
| Ecuador         | EC |
| Egitto           | EG |
| El Salvador     | SV |
| Guinea Equatoriale | GQ |
| Eritrea         | ER |
| Estonia         | EE |
| Eswatini        | SZ |
| Etiopia        | ET |
| Isole Falkland | CE |
| Faroe Islands   | DELLA |
| Figi            | FJ |
| Finlandia         | FI |
| Francia          | FR |
| Guyana francese   | GF |
| Polinesia francese | DELLE |
| Territori meridionali francesi | TF |
| Gabon           | NEI |
| Gambia          | GM |
| Georgia         | GE |
| Germania         | DE |
| Ghana           | GH |
| Gibilterra       | GI |
| Grecia          | GR |
| Groenlandia       | OpenGL |
| Grenada         | GD |
| Guadalupa      | GP |
| Guam            | GU |
| Guatemala       | GT |
| Guernsey        | GG |
| Guinea          | GN |
| Guinea-Bissau   | GW |
| Guyana          | GY |
| Haiti           | Ciao |
| Isole Heard e McDonald | HM |
| Honduras        | HN |
| Hong Kong SAR (香港特別行政區)   | HK |
| Ungheria         | HU |
| Islanda         | È |
| India           | IN |
| Indonesia       | ID |
| Iran            | IR |
| Iraq            | IQ |
| Irlanda         | IE |
| Isola di Man     | Messaggistica istantanea |
| Israele          | IL |
| Italia           | È |
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
| Kuwait (الكويت)          | KW |
| Kirghizistan      | KG |
| Laos            | Discover |
| Lettonia          | LV |
| Libano         | LB |
| Lesotho         | LS |
| Liberia         | LR |
| Libia           | LY |
| Liechtenstein   | LI |
| Lituania       | LT |
| Lussemburgo      | LU |
| SAR di Macao       | MO |
| Madagascar      | MG |
| Malawi          | MW |
| Malaysia        | MY |
| Maldive        | MV |
| Mali            | ML |
| Malta           | MT |
| Isole Marshall | MH |
| Martinica      | MQ |
| Mauritania      | Signor |
| Mauritius       | MU |
| Mayotte         | YT |
| Messico          | MX |
| Micronesia      | FM |
| Moldova         | MD |
| Monaco          | MC |
| Mongolia        | MN |
| Montenegro      | Aiutami |
| Montserrat      | MS |
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
| Macedonia settentrionale | MK |
| Isole Marianne Settentrionali | NP |
| Norvegia          | NON |
| Oman            | OM |
| Pakistan        | PK |
| Palau           | PW |
| Palestinian Authority | PS |
| Panama          | PA |
| Papua Nuova Guinea | PGGIÙ |
| Paraguay        | PY |
| Perù            | PE |
| Filippine     | PH |
| Isole Pitcairn | NP |
| Polonia          | PL |
| Portogallo        | PT |
| Portorico     | Prezzo; |
| Qatar           | QA |
| Riunione         | NUOVO |
| Romania         | RO |
| Russia          | RU |
| Ruanda          | RW |
| Saba            | XS |
| Saint Barthelemy | BL |
| Saint Kitts and Nevis | KN |
| Saint Lucia     | LC |
| Saint Martin    | MF |
| Saint Pierre e Miquelon | PM |
| Saint Vincent e Grenadine | VC |
| Samoa           | WS |
| San Marino      | SM |
| Sao Tome e Principe | ST |
| Arabia Saudita (المملكة العربية السعودية)    | SA |
| Senegal         | SN |
| Serbia          | RS |
| Seychelles      | SC |
| Sierra Leone    | Y | 
| Singapore       | SG |
| Sint Eustatius  | XE |
| Sint Maarten    | SX |
| Slovacchia        | SK |
| Slovenia        | Y |
| Isole Salomone | SB |
| Somalia         | COSÌ |
| Sudafrica    | Immagine dell'icona |
| Isole South Georgia e South Sandwich | GS |
| Sud Sudan     | SS |
| Spagna           | ES |
| Sri Lanka       | LK |
| Sant'Elena, Ascensione, Tristan da Cunha | SH |
| Sudan           | SD |
| Suriname        | RESPONSABILE |
| Svalbard        | SJ |
| Svezia          | SE |
| Svizzera     | CH |
| Siria           | SY |
| Taiwan          | TW |
| Tagikistan      | TJ |
| Tanzania        | TZ |
| Thailandia        | TH |
| Timor Est     | TL |
| Togo            | TG |
| Tokelau         | TK |
| Tonga           | A |
| Trinidad e Tobago | TT |
| Tunisia         | Tennessee |
| Turchia          | TR |
| Turkmenistan    | TM |
| Isole Turks e Caicos | TC |
| Tuvalu          | TV |
| Isole periferiche statunitensi | UM |
| Isole Vergini statunitensi | VI |
| Uganda          | UG |
| Ucraina         | UA |
| Emirati Arabi Uniti | AE |
| Regno Unito  | GB |
| Stati Uniti   | NOI |
| Uruguay         | UY |
| Uzbekistan      | UZ |
| Vanuatu         | VU |
| Città del Vaticano    | VA |
| Venezuela       | VE |
| Vietnam         | VN |
| Wallis e Futuna | WF |
| Yemen           | VOI |
| Zambia          | ZM |
| Zimbabwe        | ZW |

