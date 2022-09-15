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
ms.openlocfilehash: 0e6118e42600bda58bf7ddc9d7f8e0fee0b7ad9f
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706145"
---
# <a name="skype-for-business-online-retirement"></a>Ritiro di Skype for Business Online

Il 31 luglio 2021 Microsoft ha ritirato Skype for Business Online. Questo ritiro è stato annunciato a luglio 2019 per offrire ai clienti un preavviso di due anni per pianificare gli aggiornamenti a Microsoft Teams. Teams è l'app di base per la comunicazione e la collaborazione in Microsoft 365. Con il ritiro di Skype for Business Online, Microsoft vuole assicurarsi che i clienti dispongano delle informazioni e delle risorse necessarie per pianificare ed eseguire correttamente l'aggiornamento a Teams.  Il servizio consumer Skype non è interessato da questo ritiro. Per informazioni sui motivi per cui Skype for Business Online è stato ritirato, vedere [Domande frequenti sull'aggiornamento da Skype for Business a Microsoft Teams](FAQ-journey.yml).

Microsoft inizierà a disattivare l'infrastruttura di Skype for Business Online dal 30 giugno 2022 in poi. Inoltre, a partire da ottobre 2022, Microsoft inizierà a eliminare gli aspetti specifici dell'infrastruttura per le organizzazioni ibride. Questo articolo contiene indicazioni per le organizzazioni con TeamsSolo gli utenti aggiornati da qualsiasi versione di Skype for Business.

> [!Important]
> **Il ritiro di Skype for Business Online non influisce sul supporto per le distribuzioni locali di Skype for Business Server e Lync Server 2013**. Tuttavia, i clienti ibridi con una combinazione di utenti ospitati online e locale *devono* aggiornare tutti gli utenti *online* in modo che siano TeamsOnly. A tutti gli utenti online deve essere assegnata la modalità TeamsOnly usando TeamsUpgradePolicy. Inoltre, Microsoft fornisce aggiornamenti assistiti per automatizzare l'aggiornamento degli utenti di Skype for Business online rimanenti alla modalità TeamsOnly. Le organizzazioni ibride non devono spostare gli utenti di Skype for Business *locali* nel cloud in seguito al ritiro. *Microsoft supporta completamente le organizzazioni ibride con una combinazione di utenti di TeamsOnly e utenti di Skype for Business locali*. I clienti con distribuzioni ibride di Skype for Business Server o Lync Server 2013 devono esaminare [le implicazioni del ritiro di Skype for Business Online](/skypeforbusiness/hybrid/plan-hybrid-connectivity.md#implications-of-the-upcoming-retirement-of-skype-for-business-online).


## <a name="what-to-expect-post-retirement"></a>Cosa aspettarsi dopo il ritiro

Non è più possibile assegnare agli utenti ospitati nel cloud una modalità diversa da TeamsOnly. Questo significa che:

 - Quando si assegnano licenze a nuovi utenti che non sono ospitati in Skype for Business Server locali, agli utenti viene automaticamente assegnata la modalità TeamsOnly, indipendentemente dai criteri globali del tenant di TeamsUpgradePolicy.
 - Nelle organizzazioni ibride, quando si spostano gli utenti ospitati localmente nel cloud, agli utenti viene automaticamente assegnata la modalità TeamsOnly, indipendentemente dal fatto che l'opzione `MoveToTeams` sia stata specificata in `Move-CsUser`.
 - Agli utenti ospitati nel cloud non può essere assegnata una modalità diversa da TeamsOnly. Gli utenti ospitati online *non* usano Skype for Business server locale.

Tutti i clienti che hanno utenti rimanenti ospitati in Skype for Business Online ma non sono ancora assegnati alla modalità TeamsOnly devono assegnare la modalità TeamsOnly a questi utenti il prima possibile. Inoltre, Microsoft fornirà aggiornamenti assistiti per Skype for Business utenti online non in modalità TeamsOnly. L'esperienza di aggiornamento assistito dipende dal fatto che l'organizzazione sia un'organizzazione online pura o un'organizzazione con utenti Skype for Business locali. Per altre informazioni, vedere [Aggiornamenti assistiti da Skype for Business Online a Microsoft Teams](upgrade-assisted.md). Al termine dell'aggiornamento assistito, tutti gli utenti *online* saranno in modalità TeamsOnly. *Tutti gli utenti ospitati in locale rimangono in locale e non verranno resi TeamsOnly*.

Gli utenti in modalità TeamsSolo ricevono chat e chiamate in arrivo in Teams e pianificano anche riunioni in Teams. Non possono avviare chat o chiamate o pianificare riunioni in Skype for Business Online. Teams Solo gli utenti possono partecipare Skype for Business riunioni che già hanno o ricevono in futuro. Tuttavia, dopo che Microsoft rimuove l'infrastruttura Skype for Business Online per un determinato utente di TeamsOnly, solo gli utenti di Teams possono partecipare Skype for Business riunioni solo in forma anonima.  A partire dal 30 giugno 2022, il provisioning dei nuovi utenti di TeamsOnly non verrà più eseguito con l'infrastruttura di Skype for Business Online, quindi se vengono invitati a una riunione di Skype for Business, dovranno partecipare in forma anonima. Analogamente, il provisioning degli utenti dall'ambiente locale a Teams only nelle organizzazioni ibride non verrà più eseguito con l'infrastruttura di Skype for Business Online a partire da ottobre 2022. Se questi utenti sono invitati a una riunione di Skype for Business, dovranno partecipare anche in forma anonima.


## <a name="guidance-for-organizations-with-on-premises-deployments-of-skype-for-business-server"></a>Indicazioni per le organizzazioni con distribuzioni locali di Skype for Business Server

 - Quando si creano nuovi utenti nell'ambiente di Active Directory locale, se questi utenti verranno sincronizzati con Azure AD e si intende assegnare loro una licenza per Teams, *prima di assegnare a questi utenti la licenza*, **è necessario abilitarli nella distribuzione di Skype for Business locale e assicurarsi che la modifica sia stata sincronizzata con il cloud tramite Azure AD Connect**.  Puoi verificare che la modifica sia completamente sincronizzata con il cloud utilizzando Get-CsOnlineUser. La modifica è stata sincronizzata se l'utente HostingProvider= "SRV:".  Non dovrebbe essere "sipfed.online.lync.com".   

 - Tenere presente che Solo gli utenti di Teams dovranno partecipare in forma anonima alle riunioni Skype for Business dopo la rimozione dell'infrastruttura legacy Skype for Business Online per le organizzazioni ibride, a partire da ottobre 2022.  Per informazioni dettagliate, vedere [Cosa aspettarsi dopo il ritiro](#what-to-expect-post-retirement). In alternativa, è possibile garantire che le riunioni pianificate da tutti gli utenti (sia locali che solo di Teams) nell'organizzazione siano riunioni di Teams, che consentono di partecipare a una riunione autenticata per qualsiasi utente dell'organizzazione (soggetto a configurazione dei criteri). Per ottenere questo risultato, eseguire le operazioni seguenti:
   - Per gli utenti assegnati **solo Skype for Business** o **Skype for Business con le modalità di collaborazione di Teams**, modificare la modalità di coesistenza **in Skype for Business con collaborazione e riunioni di Teams**.  Questa modalità offre le stesse funzionalità delle altre due, tranne le nuove riunioni pianificate dall'utente saranno le riunioni di Teams invece di Skype for Business riunioni. Quando si assegna questa modalità direttamente a un utente (anziché a livello di tenant), per impostazione predefinita converte automaticamente anche le riunioni Skype for Business in riunioni di Teams organizzate da tale utente.
   - Per gli utenti in modalità Isole, è possibile richiedere loro di pianificare sempre le riunioni in Teams assegnando loro un'istanza di TeamsMeetingPolicy con PreferredMeetingProviderForIslandsMode=Teams. 
   - Per garantire che le riunioni Skype for Business esistenti vengano convertite in riunioni di Teams (ad esempio, se si hanno utenti Islands), è possibile usare Start-CsExMeetingMigration per attivare il [servizio di migrazione](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#trigger-meeting-migration-manually-via-powershell-cmdlet) delle riunioni per convertire le riunioni di un utente in Teams.
  

## <a name="actions-to-take-before-june-30-2022"></a>Azioni da intraprendere prima del 30 giugno 2022
Ora che Skype for Business Online è stato ritirato, Microsoft inizierà a disattivare l'infrastruttura di supporto non prima del 30 giugno 2022.  Per qualsiasi organizzazione con Teams Solo gli utenti aggiornati da qualsiasi versione di Skype for Business, è necessario eseguire un'azione se si applica una di queste situazioni:

- Se si hanno utenti di TeamsOnly che in precedenza avevano contatti in Skype for Business *e* che non hanno ancora eseguito l'accesso a Teams da quando è stato aggiornato.
- Se hai utenti di TeamsOnly che hanno ancora Skype for Business riunioni online che hanno organizzato prima dell'aggiornamento a TeamsOnly.

Se una di queste situazioni si applica all'organizzazione, è necessario intervenire entro il 30 giugno 2022, come descritto di seguito:

 - **Skype for Business contatti online:** dopo l'aggiornamento di un utente alla modalità TeamsOnly, la prima volta che l'utente accede a Teams, tutti i contatti esistenti nell'account di Skype for Business online dell'utente verranno migrati a Teams. Dopo che Microsoft ha rimosso l'infrastruttura di Skype for Business Online, non è più possibile eseguire la migrazione dei contatti *per gli utenti che non hanno ancora eseguito l'accesso a Teams.* Per eseguire la migrazione dei contatti da Skype for Business a Teams, Microsoft consiglia a tutti gli utenti che in precedenza avevano Skype for Business di accedere a Teams almeno una volta prima del 30 giugno 2022.

 - **Skype for Business riunioni online:** dopo l'aggiornamento di un'organizzazione a TeamsOnly, gli utenti creano tutte le nuove riunioni come riunioni di Teams. In alcuni casi, solo gli utenti di Teams possono ancora avere Skype for Business riunioni online che in precedenza avevano organizzato. Attualmente, gli utenti di Teams aggiornati e tutti i partecipanti invitati possono partecipare a queste riunioni online di Skype for Business usando il client Skype for Business. Dopo che Microsoft rimuove l'infrastruttura di Skype for Business Online per un determinato utente di TeamsOnly, tuttavia, quell'utente può partecipare alle riunioni Skype for Business solo in forma anonima e le eventuali riunioni Skype for Business online rimanenti *organizzate da tale utente* non esisteranno più. L'organizzatore e i partecipanti non potranno partecipare a queste riunioni. Se gli utenti delle organizzazioni TeamsOnly hanno altre riunioni online Skype for Business che hanno organizzato, Microsoft consiglia di ripianificare queste riunioni come riunioni di Teams. In alternativa, gli amministratori possono usare il [servizio di migrazione](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) delle riunioni per convertire queste riunioni in riunioni di Teams. In entrambi i casi, completare queste azioni entro il 30 giugno 2022.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>In che modo Microsoft aiuta i clienti a eseguire l'aggiornamento a Teams

È consigliabile iniziare subito l'aggiornamento da Skype for Business Online a Teams. Sfruttare le risorse disponibili per pianificare la distribuzione e l'aggiornamento di Teams da Skype for Business:

- [Documentazione per la distribuzione e l'aggiornamento di Teams](upgrade-start-here.md) - Guida tecnica gratuita per gli amministratori IT.

- Workshop gratuiti sulla [pianificazione dell'aggiornamento di Teams](./upgrade-workshops-landing-page.yml): workshop interattivi gratuiti sulla pianificazione dell'aggiornamento, in cui riceverai indicazioni, procedure consigliate e risorse progettate per aiutarti a pianificare e implementare l'aggiornamento a Teams.

- [Aggiornamenti assistiti da Skype for Business Online a Microsoft Teams](upgrade-assisted.md) - Programma automatizzato che consente di aggiornare Skype for Business utenti online a Teams.

- [FastTrack per Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) - Assistenza per la distribuzione di Teams disponibile per i piani idonei.

- [Formazione in tempo reale su Teams](./instructor-led-training-teams-landing-page.yml) - Corsi di formazione online gratuiti progettati per rendere l'organizzazione operativa con Teams.

- [Teams Chalk Talks](./chalk-talks-landing-page.yml) : workshop online gratuiti per professionisti IT e decisori che descrivono le procedure consigliate per scenari chiave in Teams.

- [Partner Microsoft](https://www.microsoft.com/solution-providers/home) : i provider di soluzioni Microsoft possono aiutarti a sfruttare al meglio Teams.

- [Blog di Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) - Notizie su nuove funzionalità, risorse di adozione e utilizzo, dispositivi Teams e integrazione con altre applicazioni aziendali.

Se sei un cliente corrente di Skype for Business Online, inizia subito a pianificare l'aggiornamento a Teams. Siamo entusiasti del fatto che tu possa sperimentare le sue potenti funzionalità di comunicazione e collaborazione e ci impegniamo ad aiutarti lungo il percorso.  Per altre informazioni sul ritiro di Skype for Business Online, vedi [Domande frequenti sull'aggiornamento da Skype for Business a Microsoft Teams](FAQ-journey.yml).





