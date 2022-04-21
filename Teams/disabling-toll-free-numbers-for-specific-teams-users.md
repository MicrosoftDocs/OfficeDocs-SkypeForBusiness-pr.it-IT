---
title: Disabilitazione dei numeri verdi per specifici utenti Teams
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
description: Scopri come controllare in che modo gli organizzatori possono usare i numeri verdi per le riunioni di Audioconferenza Bridge.
ms.openlocfilehash: 6d841a48381609a019a1749095aac4a95901a7c4
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016628"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Disabilitazione dei numeri verdi per specifici utenti Teams

Se la tua organizzazione dispone di numeri gratuiti nel relativo ponte per audioconferenze Microsoft, puoi consentire o impedire il loro utilizzo in riunioni di organizzatori specifici.  

Per impostazione predefinita, tutti gli utenti nell'organizzazione sono abilitati per l'utilizzo di numeri gratuiti, ovvero questi numeri, se disponibili, possono essere utilizzati dai partecipanti per partecipare alle riunioni. Se desideri che alcuni utenti all'interno dell'organizzazione siano esclusi, puoi limitare l'uso di tali numeri relativi alle riunioni per utenti specifici tramite un controllo di attivazione dei numeri gratuiti.

Quando i numeri gratuiti sono disabilitati per un determinato organizzatore:

- Un numero gratuito non verrà più incluso nel suo invito alle riunioni.
- I numeri gratuiti non verranno più elencati nella pagina "Trova un numero locale" a cui viene fatto riferimento nei suoi inviti alle riunioni.
- I partecipanti saranno in grado di partecipare alla riunione di un determinato organizzatore se compongono qualsiasi numero gratuito dell'organizzazione.
- I partecipanti possono continuare a partecipare alle riunioni dell'organizzatore tramite numeri a pagamento.

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Disattivazione dei numeri verdi per utenti specifici

È possibile disabilitare i numeri verdi per utenti specifici modificando l'impostazione di *AllowTollFreeDialIn* su **Disattivato** all'interno del *TeamsAudioConferencingPolicy* assegnato a tali utenti. Una volta disattivate le nuove riunioni create da tali utenti, non saranno inclusi numeri verdi. Ulteriori informazioni sono disponibili [nelle impostazioni dei criteri per i servizi di audioconferenza per i numeri verdi e a pagamento](audio-conferencing-toll-free-numbers-policy.md).

> [!IMPORTANT]
> Le riunioni ricorrenti precedenti e pianificate in precedenza potrebbero comunque mostrare numeri verdi e i partecipanti non potranno partecipare a tali riunioni utilizzando un numero verde. Puoi ripianificare tutte le riunioni vecchie e ricorrenti per questi utenti e rimuovere i numeri verdi utilizzando il servizio MMS.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
