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
ms.openlocfilehash: dcd2148a3f939bd8799b7b3f8b86118359936b7c
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783905"
---
# <a name="skype-for-business-online-retirement"></a>Ritiro di Skype for Business Online

Il 31 luglio 2021 Microsoft ha ritirato Skype for Business Online. Questo ritiro è stato annunciato a luglio 2019 per dare ai clienti un preavviso di due anni per pianificare gli aggiornamenti a Microsoft Teams. Teams è l'app principale per la comunicazione e la collaborazione in Microsoft 365. Con Skype for Business Online ritirato, Microsoft vuole assicurarsi che i clienti siano in grado di disporre delle informazioni e delle risorse necessarie per pianificare ed eseguire correttamente l'aggiornamento a Teams.  Il Skype consumer non è interessato da questo ritiro. Per informazioni sul motivo per cui Skype for Business Online è stato ritirato, vedere Domande frequenti sull'aggiornamento da Skype for Business [a Microsoft Teams](FAQ-journey.yml).

Microsoft inizierà a rimuovere l'infrastruttura Skype for Business Online il 30 giugno 2022 o dopo. Questo articolo contiene indicazioni per le organizzazioni con utenti di TeamsOnly che sono stati aggiornati da qualsiasi versione di Skype for Business.


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Organizzazioni con distribuzioni locali di Skype for Business Server

La ritirata Skype for Business Online non influisce sul supporto per le distribuzioni locali di Skype for Business Server e Lync Server 2013. Tuttavia, i clienti ibridi con una combinazione di utenti ospitati online e locali devono aggiornare qualsiasi *utente online* . A tutti gli utenti online deve essere assegnata la modalità TeamsOnly usando TeamsUpgradePolicy. Microsoft fornisce aggiornamenti assistiti per automatizzare l'aggiornamento degli utenti rimanenti Skype for Business online alla modalità TeamsOnly. Le organizzazioni ibride non devono spostare i propri utenti *locali* Skype for Business nel cloud in seguito a questa ritirata. Microsoft supporta completamente le organizzazioni ibride con una combinazione di utenti TeamsOnly e utenti locali Skype for Business utenti. I clienti con distribuzioni ibride di Skype for Business Server o Lync Server 2013 devono esaminare il ritiro [Skype for Business Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

## <a name="what-to-expect-post-retirement"></a>Cosa aspettarsi dopo il ritiro

Non è più possibile che agli utenti ospitati nel cloud sia assegnata una modalità diversa da TeamsOnly. Questo significa:

 - Quando si impostano le licenze per i nuovi utenti che non sono ospitati in un Skype for Business Server locale, agli utenti viene assegnata automaticamente la modalità TeamsOnly, indipendentemente dai criteri globali del tenant di TeamsUpgradePolicy.
 - Nelle organizzazioni ibride, quando si spostano utenti ospitati in locale nel cloud, agli utenti viene assegnata automaticamente la modalità TeamsOnly `MoveToTeams` indipendentemente dal fatto che il parametro sia stato specificato in `Move-CsUser`.
 - Agli utenti ospitati nel cloud non può essere assegnata una modalità diversa da TeamsOnly. Gli utenti ospitati online *non* usano Skype for Business server locale.

I clienti potrebbero avere utenti rimanenti ospitati in Skype for Business Online e a cui non è ancora assegnata la modalità TeamsOnly. I clienti devono assegnare la modalità TeamsOnly a questi utenti il prima possibile. Microsoft fornirà aggiornamenti assistiti per gli utenti Skype for Business online non in modalità TeamsOnly. L'esperienza di aggiornamento assistito dipende dal fatto che l'organizzazione sia un'organizzazione online pura o un'organizzazione con utenti locali Skype for Business utenti. Per altre informazioni, vedere [Aggiornamenti assistiti da Skype for Business Online a Microsoft Teams](upgrade-assisted.md).

Al termine dell'aggiornamento assistito, tutti gli *utenti online* saranno in modalità TeamsOnly. Gli utenti in modalità TeamsOnly ricevono chat e chiamate in Teams e pianificano anche riunioni in Teams. Non possono avviare chat o chiamate o pianificare riunioni in Skype for Business Online.  Tuttavia, gli utenti di TeamsOnly possono partecipare Skype for Business riunioni che hanno già o ricevono in futuro. Infine, *tutti gli utenti ospitati in* locale rimangono locali e non verranno resi TeamsOnly.

## <a name="actions-to-take-before-june-30-2022"></a>Azioni da eseguire prima del 30 giugno 2022
Ora che Skype for Business Online è stato ritirato, Microsoft inizierà a rimuovere l'infrastruttura di supporto non prima del 30 giugno 2022.  Per qualsiasi organizzazione con utenti teamsOnly che sono stati aggiornati da qualsiasi versione di Skype for Business, è necessario intervenire se si applica una di queste situazioni:

- Se si hanno utenti di TeamsOnly che previoulsy avevano contatti in Skype for Business e che non  hanno ancora eseguito l'accesso a Teams dall'aggiornamento.
- Se sono presenti utenti di TeamsOnly che hanno ancora Skype for Business riunioni online che hanno organizzato prima dell'aggiornamento a TeamsOnly.

Se una di queste situazioni si applica all'organizzazione, è necessario intervenire entro il 30 giugno 2022 come descritto di seguito:

 - **Skype for Business Contatti online:** dopo l'aggiornamento di un utente alla modalità TeamsOnly, la prima volta che l'utente accede a Teams, tutti i contatti esistenti nell'account Skype for Business Online dell'utente verranno migrati a Teams. Dopo che Microsoft ha rimosso l'Skype for Business Online, non è più possibile eseguire la migrazione dei contatti per gli utenti che non hanno ancora eseguito *l'accesso a Teams.* Per eseguire la migrazione dei contatti da Skype for Business a Teams, Microsoft consiglia a tutti gli utenti che in precedenza avevano Skype for Business accedere a Teams almeno una volta prima del 30 giugno 2022.

 - **Skype for Business riunioni online: dopo** l'aggiornamento di un'organizzazione a TeamsOnly, gli utenti creano tutte le nuove riunioni Teams riunioni. In alcuni casi, gli utenti di TeamsOnly potrebbero comunque Skype for Business riunioni online organizzate in precedenza. Attualmente, gli utenti di TeamsOnly aggiornati e tutti i partecipanti invitati possono partecipare a queste riunioni Skype for Business online usando il Skype for Business client. Dopo che Microsoft ha rimosso l'infrastruttura Skype for Business Online per un determinato utente di TeamsOnly, tuttavia, le riunioni Skype for Business Online rimanenti organizzate da tale utente non esisteranno più. L'organizzatore e tutti i partecipanti non potranno partecipare a queste riunioni. Se gli utenti delle organizzazioni TeamsOnly hanno ancora Skype for Business riunioni online che hanno organizzato, Microsoft consiglia di riprogrammare queste riunioni come Teams riunioni. In alternativa, gli amministratori possono usare il [servizio di migrazione delle](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) riunioni per convertire queste riunioni in Teams riunioni. In entrambi i casi, completare queste azioni entro il 30 giugno 2022.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>In che modo Microsoft aiuta i clienti ad eseguire l'aggiornamento a Teams

È consigliabile iniziare l'aggiornamento da Skype for Business Online a Teams oggi. Sfruttare le risorse disponibili per pianificare la distribuzione Teams e l'aggiornamento da Skype for Business:

- [Teams documentazione per la distribuzione e l'aggiornamento](upgrade-start-here.md): indicazioni tecniche gratuite per gli amministratori IT.

- [Teams workshop](./upgrade-workshops-landing-page.yml) di pianificazione degli aggiornamenti: laboratori gratuiti di pianificazione interattiva degli aggiornamenti, in cui si riceveranno indicazioni, procedure consigliate e risorse progettate per pianificare e implementare l'aggiornamento a Teams.

- [Aggiornamenti assistiti da Skype for Business Online a Microsoft Teams](upgrade-assisted.md) : programma automatizzato che consente di aggiornare gli utenti di Skype for Business Online a Teams.

- [FastTrack per Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365)- Teams di distribuzione disponibile per i piani idonei.

- [Teams formazione live](./instructor-led-training-teams-landing-page.yml): corsi di formazione online gratuiti progettati per far entrare in funzione l'organizzazione con Teams.

- [Teams colloqui su Gessetto](./chalk-talks-landing-page.yml): laboratori online gratuiti per professionisti IT e decisori che descrivono le procedure consigliate per gli scenari chiave in Teams.

- [Partner Microsoft](https://www.microsoft.com/solution-providers/home): i provider di soluzioni Microsoft possono aiutarti a sfruttare al meglio Teams.

- [Microsoft Teams blog](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog): Teams nuove funzionalità, risorse di adozione e utilizzo, Teams dispositivi mobili e integrazione con altre applicazioni aziendali.

Se si è un cliente Skype for Business Online, iniziare a pianificare l'aggiornamento a Teams oggi. Siamo entusiasti che l'utente sperimenti le sue potenti funzionalità di comunicazione e collaborazione e ci impegniamo a collaborare lungo il percorso.  Per altre informazioni sul ritiro Skype for Business online, vedere Domande frequenti sull'aggiornamento da Skype for Business [a Microsoft Teams](FAQ-journey.yml).





