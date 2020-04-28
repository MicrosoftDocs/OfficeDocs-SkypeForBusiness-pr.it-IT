---
title: Disabilitazione dei numeri verdi per gli utenti di team specifici
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Informazioni su come controllare il modo in cui gli organizzatori possono usare numeri verdi per le riunioni Bridge di audioconferenza.
ms.openlocfilehash: 517ffea6a15cd625320f33e3eb4911f4a250d51d
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904571"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Disabilitazione dei numeri verdi per gli utenti di team specifici

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

Dall'interfaccia di **amministrazione di Microsoft teams**:

1. Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.

2. Accanto a servizi di **audioconferenza**fare clic su **modifica**.

3. Imposta **Includi numeri verdi nelle convocazioni di riunione da questo utente** su **disattivato**. 

4. Fare clic su **Salva.** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Utilizzo di PowerShell**  

Per altre informazioni, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .
