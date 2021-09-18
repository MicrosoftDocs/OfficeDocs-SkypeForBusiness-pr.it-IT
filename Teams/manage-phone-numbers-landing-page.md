---
title: Gestire i numeri di telefono per la propria organizzazione
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: conceptual
ms.assetid: 6b61cb3c-361c-48a8-a9ef-d81bddde27bb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.overview
- ms.teamsadmincenter.voice.searchandacquire.PSTNpartner
- ms.lync.lac.NewNumberManualAcquisitionOpenSupportTicket
- ms.lync.lac.VASAMissingGeoCodes
- Calling Plans
- seo-marvel-apr2020
description: Informazioni su come ottenere e gestire i numeri di telefono degli utenti (abbonati) e dei servizi (a numero verde e a numero verde) per Microsoft Teams per l'organizzazione.
ms.openlocfilehash: d29781e16c881c9b0e00e39c6e57314c6696d8bb
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432797"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>Gestire i numeri di telefono per l'organizzazione

Attualmente, Microsoft supporta due tipi di numeri di telefono: 

- [**Numeri utente,**](#user-telephone-numbers)detti anche numeri di abbonato, che possono essere assegnati agli utenti dell'organizzazione.

- [**Numeri di**](#service-telephone-numbers)servizio, assegnati a servizi come audioconferenza, operatori [automatici](plan-auto-attendant-call-queue.md)o [code di chiamata.](plan-auto-attendant-call-queue.md) [](deploy-audio-conferencing-teams-landing-page.md)

Microsoft sta lavorando per semplificare i tipi di numero, ma per il momento è necessario decidere:

- Quali località utente hanno bisogno di nuovi numeri di telefono da Microsoft?
- Quale tipo di numero di telefono (abbonato o servizio) è necessario?
- Come si portano i numeri di telefono esistenti Teams?

La modalità di acquisizione e gestione dei numeri di telefono varia a seconda dell'opzione di connettività PSTN.

- Per informazioni sulla gestione dei numeri di telefono per Microsoft Calling Plan, vedere [Gestire i numeri di telefono per i piani per chiamate.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Per informazioni sulla gestione dei numeri di telefono Connessione con operatore, vedere Configurare i numeri di [telefono con](operator-connect-configure.md#set-up-phone-numbers)Connessione con operatore .

- Per informazioni sulla gestione dei numeri di telefono per Il routing diretto, vedere Configurare il numero di telefono [e abilitare la segreteria telefonica e la segreteria telefonica aziendale.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)

Se sono necessari tipi di numeri aggiuntivi o di altro tipo diversi da quelli presenti nell'interfaccia di amministrazione di Microsoft Teams, è possibile inviare una richiesta di numero di telefono al Centro servizi numeri [di](https://pstnsd.powerappsportals.com/)Telefono.

## <a name="user-telephone-numbers"></a>Numeri di telefono degli utenti

Esistono due tipi di numeri di telefono utente che possono essere assegnati agli utenti dell'organizzazione:  
    
- **I numeri geografici** hanno una relazione con un'area geografica e sono i più comuni. Nella maggior parte dei casi, ad esempio, i numeri di telefono geografici possono essere usati solo all'interno di un determinato indirizzo, città, stato o area geografica del paese.
    
- **I numeri non geografici** sono noti come numeri nazionali o talvolta numeri VoIP. Questi numeri non hanno una relazione con un'area geografica all'interno di un paese/area geografica. Ad esempio, i numeri non geografici spesso hanno lo stesso costo quando si chiama il numero da qualsiasi punto del paese/area geografica. Inoltre, alcuni paesi, come la Danimarca, hanno solo numeri non geografici disponibili.


## <a name="service-telephone-numbers"></a>Numeri di telefono del servizio  

Questa sezione descrive i numeri di servizio disponibili da Microsoft inclusi nelle licenze. Per informazioni sui numeri di servizio forniti da Connessione con operatore o Routing diretto, contattare il provider. 

Esistono due tipi di numeri di telefono di servizio forniti da Microsoft, a numero verde e a numero verde, che possono essere assegnati a servizi come audioconferenze, operatori automatici o code di chiamata. I numeri di servizio hanno una capacità di chiamata simultanea maggiore rispetto ai numeri utente. La disponibilità del numero di servizio varia in base al paese/area geografica e al tipo di numero (che si tratta di un numero a pedaggio o a numero verde). Le licenze di telefonia Microsoft in ogni paese/area geografica determinano per cosa può essere usato il numero.
    
 - **Numeri di servizio a pedaggio** : sono disponibili due tipi di numeri di servizio a pedaggio, che possono richiedere un costo a pedaggio per il chiamante:
    
   - **Numeri geografici** I numeri geografici hanno una relazione con un'area geografica. Nella maggior parte dei casi, ad esempio, i numeri di telefono geografici possono essere usati solo all'interno di un determinato indirizzo, città, stato o area geografica del paese.
        
   - **Numeri non geografici** I numeri non geografici sono numeri nazionali che non hanno una relazione con un'area geografica all'interno di un paese/area geografica. Ad esempio, i numeri non geografici spesso hanno lo stesso costo quando si chiama il numero da qualsiasi punto del paese/area geografica.
   
- **Numeri di servizio gratuiti:** questi numeri di servizio in genere non comportano un costo a pedaggio per il chiamante. Teams numeri verde nazionali in oltre 60 paesi/aree geografiche.
    
    > [!CAUTION]
    > Alcuni paesi/aree geografiche e i tipi di numeri di origine, ad esempio le chiamate provenienti da telefoni cellulari, possono in alcuni casi sostenere un costo a pedaggio per il chiamante. 


    
  
> [!NOTE]
> Se è necessario ottenere un numero di telefono maggiore di questo, contattare il [Telefono Servizio](https://pstnsd.powerappsportals.com/)clienti.