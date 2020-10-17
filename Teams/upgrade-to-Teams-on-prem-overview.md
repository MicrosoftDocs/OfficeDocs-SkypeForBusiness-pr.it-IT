---
title: Eseguire l'aggiornamento a teams da una distribuzione locale di Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: 528dcfd975616d213b8a9fbd2499dc5d798708b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533583"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Eseguire l'aggiornamento da Skype for business a teams &mdash; per gli amministratori IT

## <a name="overview"></a>Panoramica

Quando si esegue l'aggiornamento da Skype for business a teams, alcune organizzazioni richiedono un'implementazione progressiva progettata e gestita dai rispettivi reparti IT. Gli articoli di questa sezione si applicano principalmente agli amministratori IT delle organizzazioni di grandi dimensioni. Queste organizzazioni sono in genere locali, ma potrebbero anche essere grandi organizzazioni di Skype for business online. Prima di leggere questi articoli, leggere introduzione all' [aggiornamento dei team](upgrade-start-here.md) e [informazioni sul Framework di aggiornamento](upgrade-framework.md).


Gli articoli seguenti ti guideranno nel processo di aggiornamento per l'organizzazione: 

- [Metodi di aggiornamento](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Strumenti per la gestione dell'aggiornamento](upgrade-to-teams-on-prem-tools.md)
- [Considerazioni aggiuntive per le organizzazioni con Skype for business locale](upgrade-to-teams-on-prem-considerations.md)
- [Implementare l'aggiornamento](upgrade-to-teams-on-prem-implement.md)
- [Considerazioni su PSTN (Public Switched Telephone Network)](upgrade-to-teams-on-prem-pstn-considerations.md)

Gli articoli seguenti descrivono inoltre importanti concetti di aggiornamento e comportamenti di coesistenza:

- [Coesistenza di teams e Skype for business](upgrade-to-teams-on-prem-coexistence.md)
- [Modalità di coesistenza-riferimento](migration-interop-guidance-for-teams-with-skype.md)
- [Esperienza del client di Teams e conformità alle modalità di coesistenza](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>Questi articoli usano i termini Skype for business online, Skype for Business Server locale e Skype for business. Quest'ultimo termine si riferisce sia alle versioni online che a quelle locali.

Prima di iniziare, tieni presente che un utente che ha eseguito la migrazione a teams non usa più un client Skype for business tranne che per partecipare a una riunione ospitata in Skype for business.  Tutte le chat in arrivo e le chiamate atterrano nel client Teams dell'utente, indipendentemente dal fatto che il mittente usi team o Skype for business. Tutte le nuove riunioni organizzate dall'utente migrato saranno programmate come riunioni teams. Se l'utente tenta di usare il client Skype for business, l'avvio delle chat e delle chiamate è bloccato.  L'utente può comunque usare il client Skype for business per partecipare a riunioni Skype for business a cui sono invitati. I client Skype for business meno recenti forniti prima di 2017 non onorano TeamsUpgradePolicy. Verificare che si stia usando il client Skype for business più recente.
 
Puoi gestire la transizione dell'utente a teams usando il concetto di [modalità](migration-interop-guidance-for-teams-with-skype.md), che è una proprietà di [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Un utente che ha eseguito la migrazione a teams come descritto in precedenza è in modalità "TeamsOnly".  Per un'organizzazione che sta migrando a teams, l'obiettivo finale è quello di trasferire tutti gli utenti alla modalità TeamsOnly.

>[!NOTE]
>Gli utenti che hanno un account locale di Skype for business non possono essere TeamsOnly. Anche se questi utenti possono [usare teams in modalità Islands](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), questo non offre il set completo di funzionalità teams disponibile in modalità TeamsOnly. Per rendere questi utenti TeamsOnly, è necessario spostarli nel cloud usando gli `Move-CsUser` strumenti di Skype for Business Server locale.

Ok. Iniziamo.  Il primo passaggio consiste nel comprendere i [metodi di aggiornamento disponibili](upgrade-to-teams-on-prem-upgrade-methods.md).







   

## <a name="related-links"></a>Collegamenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

