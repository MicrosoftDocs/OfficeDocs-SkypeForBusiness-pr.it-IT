---
title: Ritiro di Skype for Business Online
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Informazioni sul piano di ritiro per Skype for Business Online e su come Microsoft aiuta i clienti a eseguire la migrazione a Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6c18871756c8081b7013666d98d1599cfec4117f
ms.sourcegitcommit: b635f3765498ae23f535a33fa9ffea5068eecb14
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2022
ms.locfileid: "63463739"
---
# <a name="skype-for-business-online-retirement"></a>Ritiro di Skype for Business Online

Il 31 luglio 2021 Microsoft ha ritirato Skype for Business Online. Questo ritiro è stato annunciato a luglio 2019 per dare ai clienti un preavviso di due anni per pianificare gli aggiornamenti a Microsoft Teams. Teams è l'app principale per la comunicazione e la collaborazione in Microsoft 365. Con Skype for Business Online ritirato, Microsoft vuole assicurarsi che i clienti siano in grado di disporre delle informazioni e delle risorse necessarie per pianificare ed eseguire correttamente l'aggiornamento a Teams.  Il Skype consumer non è interessato da questo ritiro.

## <a name="why-is-skype-for-business-online-retiring"></a>Perché Skype for Business online si ritira?

Dalla sua introduzione, Skype for Business Online è stato uno strumento prezioso per milioni di persone in tutto il mondo. Combinando messaggistica istantanea, chiamate e video, Skype for Business Online ha stabilito nuove possibilità per le comunicazioni aziendali. Teams è il prossimo capitolo di questa visione. 

Le funzionalità di Microsoft Teams vanno oltre quelle di Skype for Business Online. L'innovazione e lo sviluppo della piattaforma Teams gli utenti beneficiano di prestazioni, funzionalità, flessibilità e sicurezza più avanzate. Combinando le funzionalità seguenti in un'unica esperienza, Teams nuovi modi di lavorare:

- Chat
- Video
- Chiamate
- Collaborazione ai documenti
- Integrazione delle applicazioni

Teams è più di un aggiornamento per Skype for Business Online. Si tratta di un potente strumento che consente a scuole e organizzazioni di diventare più agile e di migliorare l'efficienza dei flussi di lavoro chiave. Per altre informazioni sui vantaggi di Teams, vedere il white paper forrester [The Total Economic Impact™ of Microsoft Teams](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/sites/2/2019/04/Total-Economic-Impact-Microsoft-Teams.pdf?rtc=1).

Per altre informazioni sul ritiro Skype for Business online, vedere Domande frequenti sull'aggiornamento da Skype for Business [a Microsoft Teams](FAQ-journey.yml).

## <a name="organizations-with-skype-for-business-online"></a>Organizzazioni con Skype for Business Online

Microsoft fornisce un processo di aggiornamento assistito per aiutare le organizzazioni a spostare gli utenti rimanenti Skype for Business Online Teams solo. Teams è disponibile nella maggior parte dei piani Microsoft 365 Business e Enterprise e gli investimenti in licenze esistenti vengono Teams. Le capacità che oggi sono carichi di lavoro Premium in Skype for Business Online continueranno a essere carichi di lavoro Premium in Teams. Ad esempio, se sono state acquistate audioconferenze autonome o come parte di E5 con Skype for Business, le audioconferenze verranno abilitate in Teams.

## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organizzazioni con distribuzioni locali di Skype for Business Server

Il ritiro di Skype for Business Online non influisce sul supporto per le distribuzioni locali di Skype for Business Server e Lync Server 2013. Tuttavia, i clienti ibridi con una combinazione di utenti ospitati online e locali devono aggiornare qualsiasi *utente online* . A questi utenti online deve essere assegnata Teams modalità Solo con TeamsUpgradePolicy. Microsoft fornisce aggiornamenti assistiti per automatizzare l'aggiornamento degli utenti rimanenti Skype for Business online alla Teams solo utenti. Le organizzazioni ibride non devono spostare *gli utenti locali* Skype for Business utenti nel cloud come risultato di questa ritirata. Microsoft supporta completamente le organizzazioni ibride con una combinazione di Teams solo gli utenti e gli utenti locali Skype for Business locali. I clienti con distribuzioni ibride di Skype for Business Server o Lync Server 2013 devono esaminare le implicazioni del prossimo ritiro di [Skype for Business Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

## <a name="what-to-expect-post-retirement"></a>Cosa aspettarsi dopo il ritiro

Non è più possibile che agli utenti ospitati nel cloud sia assegnata una modalità diversa da TeamsOnly. Questo significa:
 - Quando si impostano le licenze per i nuovi utenti (ad eccezione degli utenti ospitati in un Skype for Business Server locale), agli utenti viene assegnata automaticamente la modalità TeamsOnly, indipendentemente dai criteri globali del tenant di TeamsUpgradePolicy.
 - Nelle organizzazioni ibride, quando si spostano gli utenti ospitati in locale nel cloud, agli utenti viene assegnata automaticamente la modalità TeamsOnly ( `MoveToTeams` che indica se l'opzione è stata specificata in `Move-CsUser`.
 - Agli utenti ospitati nel cloud Skype for Business (ad esempio, non usano un  server locale) non può essere assegnata una modalità diversa da Teams solo.

I clienti potrebbero avere parti rimanenti della popolazione di utenti ospitate in Skype for Business Online e a cui non è ancora assegnata Teams modalità Solo utenti.  I clienti devono assegnare Teams modalità Solo a questi utenti il prima possibile.  Inoltre, Microsoft fornirà aggiornamenti assistiti per gli utenti Skype for Business Online non in Teams modalità Solo utenti.  L'esperienza di aggiornamento assistito dipende dal fatto che l'organizzazione sia un'organizzazione online pura o un'organizzazione con utenti locali Skype for Business utenti.  Per altre informazioni, vedere [Aggiornamenti assistiti da Skype for Business Online a Microsoft Teams](upgrade-assisted.md).

Al termine dell'aggiornamento assistito, tutti gli *utenti online* saranno in modalità Teams solo assistenza. Gli utenti in Teams modalità Solo in arrivo ricevono chat e chiamate in Teams e pianificano anche riunioni in Teams. Non possono avviare chat o chiamate o pianificare riunioni in Skype for Business Online.  Tuttavia, Teams solo gli utenti possono partecipare a Skype for Business riunioni già presenti o ricevute in futuro. Infine, *tutti gli utenti ospitati* in locale rimangono locali e non vengono resi disponibili solo Teams utenti.


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>In che modo Microsoft aiuta i clienti ad eseguire l'aggiornamento a Teams

È consigliabile iniziare l'aggiornamento da Skype for Business Online a Teams oggi.

Sfruttare le risorse disponibili per pianificare la distribuzione Teams e l'aggiornamento da Skype for Business:

- [Teams documentazione per la distribuzione e l'aggiornamento](upgrade-start-here.md): indicazioni tecniche gratuite per gli amministratori IT.

- [Teams workshop](./upgrade-workshops-landing-page.yml) di pianificazione degli aggiornamenti: laboratori gratuiti di pianificazione interattiva degli aggiornamenti, in cui si riceveranno indicazioni, procedure consigliate e risorse progettate per pianificare e implementare l'aggiornamento a Teams.

- [Aggiornamenti assistiti da Skype for Business Online a Microsoft Teams](upgrade-assisted.md) : programma automatizzato che consente di aggiornare gli utenti di Skype for Business Online a Teams.

- [FastTrack per Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365)- Teams di distribuzione disponibile per i piani idonei.

- [Teams formazione live](./instructor-led-training-teams-landing-page.yml): corsi di formazione online gratuiti progettati per far entrare in funzione l'organizzazione con Teams.

- [Teams colloqui su Gessetto](./chalk-talks-landing-page.yml): laboratori online gratuiti per professionisti IT e decisori che descrivono le procedure consigliate per gli scenari chiave in Teams.

- [Partner Microsoft](https://www.microsoft.com/solution-providers/home): i provider di soluzioni Microsoft possono aiutarti a sfruttare al meglio Teams.

- [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog): Teams nuove funzionalità, risorse di adozione e utilizzo, Teams dispositivi mobili e integrazione con altre applicazioni aziendali.

Se si è un cliente Skype for Business Online, iniziare a pianificare l'aggiornamento a Teams oggi. Siamo entusiasti che l'utente sperimenti le sue potenti funzionalità di comunicazione e collaborazione e ci impegniamo a collaborare lungo il percorso.




