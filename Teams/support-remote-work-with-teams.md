---
title: Supporto per i lavoratori remoti con Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: dansteve
localization_priority: Priority
search.appverid: MET150
description: Usare questa guida per aiutare gli utenti dell'organizzazione che lavorano da remoto a essere produttivi con Microsoft Teams, in particolare se lavorano da casa in risposta all'epidemia di COVID-19 (Coronavirus).
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80af76906697ef2510fe75d8764e8908cdbbd976
ms.sourcegitcommit: ed0ecb3b1250a23d3b91a5a33256aee1c3119db1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374313"
---
# <a name="support-remote-workers-using-microsoft-teams"></a>Supporto per i lavoratori remoti con Microsoft Teams

Usare le procedure consigliate contenute in questo articolo per supportare gli utenti che lavorano da remoto o da casa.

## <a name="technical"></a>Guide tecniche

1.  Assicurarsi che [Teams sia attivo per tutti gli utenti](assign-teams-licenses.md)
    
      - Consultare [Teams E1 Trial](e1-trial-license.md), [Teams Exploratory](teams-exploratory.md) o [Teams gratuito](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c) per rendere Teams disponibile per tutti gli utenti dell'organizzazione.

      - I dipendenti remoti fanno un uso maggiore di riunioni e audioconferenze. Se questi carichi di lavoro non sono stati ancora distribuiti, vedere [Riunioni e conferenze in Teams](deploy-meetings-microsoft-teams-landing-page.md).

2.  Informare gli utenti su Teams. Scaricare il [Customer Success Kit di Teams](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) per ottenere presentazioni, messaggi di posta elettronica di esempio, poster e guide introduttive.


5.  Assicurarsi che i dipendenti abbiano accesso a Internet e larghezza di banda adeguati per Teams. Per informazioni a questo proposito, vedere [Preparare la rete dell'organizzazione per Teams](prepare-network.md).
    - La larghezza di banda limitata può influire sulla qualità audio nelle riunioni di Teams. Per garantire la miglior esperienza di riunione in condizioni di larghezza di banda ridotta, invitare gli utenti a limitare il video e usare la rete PSTN per le chiamate e l'audio della riunione. 

    - Se si ha bisogno di assistenza per la risoluzione dei problemi relativi alla qualità delle chiamate o delle riunioni, seguire le indicazioni in [Problema noto: chiamare ID conferenza di Skype for Business/Teams](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids) in fondo all'articolo.

2.  [Inviare collegamenti alle risorse di formazione](enduser-training.md) per aiutare i dipendenti a sfruttare al meglio Teams.
    
3. Leggere i nuovi contenuti sul lavoro in remoto e condividerli con gli utenti:
        
      - Blog di Teams (28 febbraio 2020): [4 tips for working from home with Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083) (quattro suggerimenti per lavorare da casa con Microsoft Teams)

      - [Collaborare con Office 365](https://support.office.com/article/Collaborate-with-Office-365-ac05a41e-0b49-4420-9ebc-190ee4e744f4)

      - [Lavorare in remoto con Teams e Office 365](https://support.microsoft.com/help/4549995/working-remotely-with-teams-and-office-365)

3.  Invitare tutti a [installare](get-clients.md#mobile-clients) e usare l'app per dispositivi mobili: [iOS](https://go.microsoft.com/fwlink/?LinkId=835758)   [Android](https://go.microsoft.com/fwlink/p/?linkid=2102168)

    > [!NOTE]
    > Se ci si trova in Cina, passare a [Ottenere Teams per Android in Cina](get-teams-android-in-china.md)

4.  Aumentare il personale dell'[helpdesk](troubleshoot-installation.md) per gestire le richieste degli utenti.


## <a name="communications"></a>Comunicazioni

Usare Teams per rimanere in contatto con i dipendenti:
- [Team a livello di organizzazione](create-an-org-wide-team.md) e modello di app [Company Communicator](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator)
    
- Inviare informazioni sui criteri dell'organizzazione per il lavoro da casa e in materia di salute e sicurezza.
    
- Usare [Eventi live](teams-live-events/what-are-teams-live-events.md) per le riunioni a livello aziendale. Per ogni riunione di oltre 250 partecipanti, creare un evento live. 

## <a name="personal-considerations"></a>Considerazioni personali

Ecco alcuni suggerimenti per lavorare in modo efficace da casa:

- Predisporre uno spazio di lavoro fisico con una buona ergonomia e un'illuminazione appropriata.

- Definire chiaramente gli orari lavorativi e gli impegni e usare lo [stato di presenza](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e) di Teams per indicare quando si è lontani.

- Telelavoro non vuol dire che stare in casa equivale a stare in ufficio: passare intenzionalmente dall'orario "ufficio" all'orario "sono tornato a casa".

- Alzarsi periodicamente e fare una pausa. Fare una tazza di tè, una passeggiata o un po' di stretching.

## <a name="known-issue-dialing-into-skype-for-business-or-teams-conference-ids"></a>Problema noto: chiamare ID conferenza di Skype for Business o Teams

Di seguito è riportato il riepilogo di un post del Centro messaggi del 7 febbraio 2020 (MC203397):

Microsoft è a conoscenza del fatto che alcuni utenti dell'area Cina stanno riscontrando problemi nel chiamare ID conferenza di Skype for Business o Teams. Nella maggior parte dei casi, questi problemi sono esterni ai sistemi sotto il nostro controllo. Spesso il problema riguarda gli operatori di telefonia fissa e mobile locali. 

Ecco le soluzioni consigliate se si verificano problemi con le audioconferenze:

- Chiedere al chiamante o all'organizzatore della riunione di chiamare il proprio numero PSTN o di cellulare
- Partecipare alla chiamata o alla riunione dai client desktop o per dispositivi mobili usando VoIP

Se è necessario creare a un ticket di supporto, includere:
    
- Ora esatta della chiamata
- Numero del bridge di conferenza composto
- Rete telefonica del chiamante
- Numero di telefono del chiamante
