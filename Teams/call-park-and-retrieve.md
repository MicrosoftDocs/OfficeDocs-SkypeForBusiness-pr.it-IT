---
title: Chiamare il parco e recuperare in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Informazioni su come usare il parco chiamate e recuperare per mettere una chiamata in attesa in Microsoft Teams.
ms.openlocfilehash: d49e6a5a9bc25a0c7a3e25d548e2743b7f4584fb
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278716"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Chiamare il parco e recuperare in Microsoft Teams

Il "call park and retrieve" è una funzionalità che consente a un utente di mettere in attesa una chiamata. Quando una chiamata è in stato di parked, il servizio genera un codice univoco per il recupero delle chiamate. L'utente che ha parcheggiato la chiamata o qualcun altro può quindi usare quel codice con un'app o un dispositivo supportato per recuperare la chiamata. Per informazioni [dettagliate, vedere "Parco di](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) una chiamata in Teams".

Di seguito sono riportati alcuni degli scenari comuni in cui viene utilizzato il parco delle chiamate:

- Un addetto alla reception può chiamare qualcuno che lavora in una fabbrica. L'addetto della reception enuncia quindi la chiamata e il numero di codice sul sistema di indirizzi pubblici. L'utente a cui è stata chiamata può quindi prelevare un telefono Teams nell'area di produzione e immettere il codice per recuperare la chiamata.
- Un utente può eseguire una chiamata su un dispositivo mobile perché la batteria del dispositivo sta per esaurimento. L'utente può quindi immettere il codice per recuperare la chiamata da un telefono da tavolo di Teams.
- Un rappresentante del supporto ha chiamato una cliente e invia un annuncio su un canale di Teams a un esperto per recuperare la chiamata e aiutare il cliente. Un esperto immette il codice nei client di Teams per recuperare la chiamata

Per poter effettuare e recuperare chiamate, è necessario che l'utente sia VoIP aziendale un utente specifico e che sia incluso nei criteri per il parco chiamate.

> [!NOTE]
> Il parco chiamate e il recupero sono disponibili solo in modalità [di distribuzione di Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) e non sono supportati sui telefoni IP di Skype for Business.

## <a name="configure-call-park-and-retrieve"></a>Configurare il parco chiamate e recuperarlo

È necessario essere un amministratore di Teams per configurare il parco chiamate e recuperarlo. Per impostazione predefinita, l'opzione è disabilitata. È possibile abilitarla per gli utenti e creare gruppi di utenti usando i criteri per il parco chiamate. Quando si applicano gli stessi criteri a un set di utenti, questi possono effettuare un parco e recuperare le chiamate tra loro.

Per abilitare i criteri di un parco chiamate

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa ai **criteri di** parco delle  >  **chiamate vocali.**
2. Nella scheda **Gestisci criteri** fare clic su **Aggiungi.**
3. Assegnare un nome al criterio e quindi attivare Consenti il **parco** **chiamate.**

    ![Schermata delle impostazioni dei criteri di parco chiamate](media/call-park-add-policy.png)

4. Selezionare **Salva**.

È possibile modificare il criterio selezionandolo nell'elenco e facendo clic su **Modifica.**

Per il funzionamento, il criterio deve essere assegnato agli utenti. È possibile [assegnare il criterio agli utenti singolarmente](assign-policies.md) o assegnarli a un gruppo.

Per assegnare criteri per le parti di chiamata a un gruppo

1. Nella pagina Criteri per il  parco **chiamate** fare clic su Aggiungi gruppo nella scheda Assegnazione di Criteri di **gruppo.**
2. Cercare il gruppo da usare e quindi fare clic su **Aggiungi.**
3. Scegliere un rango rispetto alle altre assegnazioni di gruppo.
4. In **Seleziona un criterio** scegliere il criterio a cui assegnare il gruppo.

    ![park policies image](media/call-park-assign-policy-to-group.png)

5. Selezionare **Applica.**

## <a name="related-topics"></a>Argomenti correlati

[Parco di una chiamata in Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Assegnare i criteri agli utenti in Teams](assign-policies.md)

[New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
