---
title: Eseguire l'aggiornamento a Teams da una distribuzione locale di Skype for Business - Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578399"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Eseguire l'aggiornamento da Skype for Business a Teams &mdash; per amministratori IT

## <a name="overview"></a>Panoramica

Durante l'aggiornamento da Skype for Business a Teams, alcune organizzazioni richiedono un'implementazione progressiva pianificata e gestita dai reparti IT. Gli articoli di questa sezione sono applicabili principalmente agli amministratori IT di organizzazioni di grandi dimensioni. Queste organizzazioni sono in genere locali, ma potrebbero anche essere grandi organizzazioni Skype for Business online. Prima di leggere questi articoli, assicurarsi di leggere Guida introduttiva all'aggiornamento di [Teams](upgrade-start-here.md) [e Informazioni sul framework di aggiornamento.](upgrade-framework.md)


Gli articoli seguenti guidano il processo di aggiornamento per l'organizzazione: 

- [Metodi di aggiornamento](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Strumenti per la gestione dell'aggiornamento](upgrade-to-teams-on-prem-tools.md)
- [Considerazioni aggiuntive per le organizzazioni con Skype for Business locale](upgrade-to-teams-on-prem-considerations.md)
- [Implementare l'aggiornamento](upgrade-to-teams-on-prem-implement.md)
- [Considerazioni sulla rete PSTN (Public Switched Telephone Network)](upgrade-to-teams-on-prem-pstn-considerations.md)

Gli articoli seguenti descrivono inoltre concetti importanti sull'aggiornamento e comportamenti di coesistenza:

- [Coesistenza di Teams e Skype for Business](upgrade-to-teams-on-prem-coexistence.md)
- [Modalità di coesistenza - Riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>In questi articoli vengono utilizzati i termini Skype for Business online, Skype for Business Server locale e Skype for Business. Quest'ultimo termine fa riferimento sia alle versioni online che a versioni locali.

Prima di iniziare, tenere presente che un utente migrato a Teams non usa più un client Skype for Business se non per partecipare a una riunione ospitata in Skype for Business.  Tutte le chat e le chiamate in arrivo vengono effettuate nel client Teams dell'utente, indipendentemente dal fatto che il mittente usi Teams o Skype for Business. Tutte le nuove riunioni organizzate dall'utente di cui è stata eseguita la migrazione verranno pianificate come riunioni di Teams. Se l'utente prova a usare il client Skype for Business, l'avvio delle chat e delle chiamate viene bloccato.  Tuttavia, l'utente può (e deve) continuare a usare il client Skype for Business per partecipare alle riunioni Skype for Business a cui è stato invitato. I client Skype for Business precedenti al 2017 non rispettano il TeamsUpgradePolicy. Accertati di utilizzare l'ultima versione del client Skype for Business.
 
Puoi gestire la transizione dell'utente a Teams utilizzando il concetto di [modalità,](migration-interop-guidance-for-teams-with-skype.md)che è una proprietà di [TeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) Un utente migrato a Teams come descritto in precedenza è in modalità "TeamsOnly".  Per un'organizzazione che sta eseguendo la migrazione a Teams, l'obiettivo finale è spostare tutti gli utenti in modalità TeamsOnly.

>[!NOTE]
>Gli utenti che dispongono di un account Skype for Business locale non possono essere TeamsOnly. Anche se questi utenti [possono usare Teams in](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)modalità Isole, questo non fornisce il set completo di funzionalità di Teams disponibile in modalità TeamsOnly. Per rendere questi utenti TeamsOnly, devono essere spostati nel cloud usando gli strumenti locali di `Move-CsUser` Skype for Business Server.

Ok. Iniziamo.  Il primo passaggio consiste nel comprendere i [metodi di aggiornamento disponibili.](upgrade-to-teams-on-prem-upgrade-methods.md)







   

## <a name="related-links"></a>Collegamenti correlati

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio MMS (Meeting Migration Service)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

