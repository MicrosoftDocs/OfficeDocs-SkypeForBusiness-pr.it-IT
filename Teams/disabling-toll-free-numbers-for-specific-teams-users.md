---
title: Disabilitazione dei numeri verde per utenti Teams utenti
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Informazioni su come controllare in che modo gli organizzatori possono usare i numeri verde per le riunioni del Bridge di audioconferenza.
ms.openlocfilehash: 18696143930c42649304bb62b5693e95179397e4
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055436"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Disabilitazione dei numeri verde per utenti Teams utenti

Se la tua organizzazione dispone di numeri gratuiti nel relativo ponte per audioconferenze Microsoft, puoi consentire o impedire il loro utilizzo in riunioni di organizzatori specifici.  

Per impostazione predefinita, tutti gli utenti nell'organizzazione sono abilitati per l'utilizzo di numeri gratuiti, ovvero questi numeri, se disponibili, possono essere utilizzati dai partecipanti per partecipare alle riunioni. Se desideri che alcuni utenti all'interno dell'organizzazione siano esclusi, puoi limitare l'uso di tali numeri relativi alle riunioni per utenti specifici tramite un controllo di attivazione dei numeri gratuiti.

Quando i numeri gratuiti sono disabilitati per un determinato organizzatore:

- Un numero gratuito non verrà più incluso nel suo invito alle riunioni.
- I numeri gratuiti non verranno più elencati nella pagina "Trova un numero locale" a cui viene fatto riferimento nei suoi inviti alle riunioni.
- I partecipanti saranno in grado di partecipare alla riunione di un determinato organizzatore se compongono qualsiasi numero gratuito dell'organizzazione.
- Tutte le riunioni dell'organizzatore verranno ripianificate automaticamente e verrà rimosso il numero gratuito.  

    > [!IMPORTANT]
    > Quindi verranno inviati nuovamente tutti gli inviti di posta elettronica dell'organizzatore ai partecipanti di quelle riunioni.

- I partecipanti possono continuare a partecipare alle riunioni dell'organizzatore tramite numeri a pagamento.

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Disattivazione dei numeri verdi per utenti specifici

**Nell'Microsoft Teams di amministrazione:**

1. Nel riquadro di spostamento sinistro fare clic **su Utenti** e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Accanto a **Audioconferenza** fare clic su **Modifica.**

3. Impostare **Includi numeri verde nelle convocazioni di riunione di questo utente su** **Disattivato.**

4. Fare clic **su Salva.**

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-powershell"></a>Utilizzo di PowerShell

Per altre [informazioni, Microsoft Teams informazioni di riferimento su PowerShell.](/powershell/module/teams/?view=teams-ps)
