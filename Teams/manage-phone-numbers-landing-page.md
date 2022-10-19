---
title: Gestire i numeri di telefono per la propria organizzazione
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jenstr
ms.topic: conceptual
ms.assetid: 6b61cb3c-361c-48a8-a9ef-d81bddde27bb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
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
description: Scopri come ottenere e gestire i numeri di telefono degli utenti (abbonati) e dei servizi (a pagamento e a numero verde) per Microsoft Teams per la tua organizzazione.
ms.openlocfilehash: 52069029e7dca69f5df9520ad1491464bf6b9aa9
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584236"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>Gestire i numeri di telefono per l'organizzazione

Attualmente Microsoft supporta due tipi di numeri di telefono: 

- [**Numeri utente**](#user-telephone-numbers), detti anche numeri di abbonati, che possono essere assegnati agli utenti dell'organizzazione.

- [**Numeri di servizio**](#service-telephone-numbers) assegnati a servizi quali [Audioconferenze](deploy-audio-conferencing-teams-landing-page.md), [Operatori automatici](plan-auto-attendant-call-queue.md) o [Code di chiamata](plan-auto-attendant-call-queue.md).

Microsoft sta lavorando per semplificare i tipi di numero, ma per il momento dovrai decidere:

- Quali posizioni degli utenti richiedono nuovi numeri di telefono da Microsoft?
- Quale tipo di numero di telefono (abbonato o servizio) mi serve?
- Ricerca per categorie trasferire numeri di telefono esistenti in Teams?

La modalità di acquisizione e gestione dei numeri di telefono varia in base all'opzione di connettività PSTN (Public Switched Telephone Network).

- Per informazioni sulla gestione dei numeri di telefono per il piano per chiamate Microsoft, vedi [Gestire i numeri di telefono per i piani per chiamate](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Per informazioni sulla gestione dei numeri di telefono per Operator Connect, vedi [Configurare i numeri di telefono con Operator Connect](operator-connect-configure.md#set-up-phone-numbers).

- Per informazioni sulla gestione dei numeri di telefono per Teams Phone Mobile, vedere [Configurare i numeri di telefono con Teams Phone Mobile](operator-connect-mobile-configure.md#set-up-phone-numbers).

- Per informazioni sulla gestione dei numeri di telefono per l'instradamento diretto, vedere [Configurare il numero di telefono e abilitare la voce aziendale](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).




> [!NOTE]
> Se hai bisogno di altri tipi di numero diversi da quelli visualizzati nell'interfaccia di amministrazione di Microsoft Teams, puoi inviare una richiesta di numero di telefono al [Centro assistenza numeri di telefono](https://pstnsd.powerappsportals.com/).

## <a name="user-telephone-numbers"></a>Numeri di telefono utente

Esistono due tipi di numeri di telefono utente, che possono essere assegnati agli utenti dell'organizzazione:  
    
- **I numeri geografici** hanno una relazione con un'area geografica e sono i più comuni. Ad esempio, i numeri di telefono geografici nella maggior parte dei casi possono essere usati solo all'interno di un determinato indirizzo, città, stato o area geografica del paese.
    
- **I numeri non geografici** sono noti come numeri nazionali o a volte numeri VoIP. Questi numeri non hanno una relazione con un'area geografica all'interno di un paese/area geografica. Ad esempio, i numeri non geografici spesso hanno lo stesso costo quando si chiama il numero da un punto qualsiasi all'interno del paese o dell'area geografica. Inoltre, in alcuni paesi, ad esempio la Danimarca, sono disponibili solo numeri non geografici.


## <a name="service-telephone-numbers"></a>Numeri di telefono di servizio  

Questa sezione descrive i numeri di servizio disponibili da Microsoft inclusi nelle licenze. Per informazioni sui numeri di servizio forniti da Operator Connect o Direct Routing, contatta il provider. 

Microsoft fornisce due tipi di numeri di servizio, a pagamento e a numero verde, che possono essere assegnati a servizi quali Audioconferenze, Operatori automatici o Code di chiamata. I numeri di servizio hanno una capacità di chiamata simultanea superiore rispetto ai numeri utente. La disponibilità del numero di servizio varia in base al paese/area geografica e al tipo di numero (che si tratti di un numero a pagamento o verde). Le licenze di telefonia Microsoft in ogni paese/area geografica determinano per cosa può essere utilizzato il numero.
    
 - **Numeri di servizio a** pagamento - Esistono due tipi di numeri di servizio a pagamento, che possono comportare un costo a pagamento per il chiamante:
    
   - **Numeri geografici** I numeri geografici hanno una relazione con un'area geografica. Ad esempio, i numeri di telefono geografici nella maggior parte dei casi possono essere usati solo all'interno di un determinato indirizzo, città, stato o area geografica del paese.
        
   - **Numeri non geografici** I numeri non geografici sono numeri nazionali che non hanno una relazione con un'area geografica all'interno di un paese/area geografica. Ad esempio, i numeri non geografici spesso hanno lo stesso costo quando si chiama il numero da un punto qualsiasi all'interno del paese o dell'area geografica.
   
- **Numeri verdi** - Questi numeri di servizio in genere non comportano costi a pagamento per il chiamante. Teams fornisce numeri verdi nazionali in oltre 60 paesi/aree geografiche.
    
    > [!CAUTION]
    > Alcuni paesi/aree geografiche e tipi di numeri di origine, ad esempio le chiamate provenienti da telefoni cellulari, in alcuni casi possono comportare costi a pagamento per il chiamante. 

## <a name="where-phone-numbers-are-managed"></a>Dove vengono gestiti i numeri di telefono

Dove e come vengono gestiti i numeri dipendono dall'opzione di connettività PSTN:

- I numeri di telefono Microsoft Calling Plan e Operator Connect possono essere gestiti solo in Microsoft 365.

- I numeri di telefono direct routing possono essere gestiti nel Active Directory locale o in Microsoft 365, come descritto nelle sezioni seguenti.

### <a name="direct-routing-numbers-managed-in-an-on-premises-active-directory"></a>Numeri di routing diretto gestiti in un Active Directory locale

Se si dispone o si ha una distribuzione ibrida Skype for Business Server, è probabile che il Active Directory locale si sincronizzi con Microsoft 365. Ciò significa che gli attributi della directory per gli account utente e delle risorse vengono gestiti nel Active Directory locale e sincronizzati in Microsoft 365.

Se il numero di telefono routing diretto è gestito sull'account utente o della risorsa nel Active Directory locale, il parametro msRTCSIP-Line dell'account contiene un valore. È possibile usare uno strumento come ADSI Edit per visualizzare il parametro msRTCSIP-Line per un account utente o di risorsa a cui è assegnato un numero di telefono routing diretto in Active Directory locale.   

Dopo aver sincronizzato automaticamente questo parametro con l'account utente o della risorsa in Microsoft 365 tramite il processo di sincronizzazione della directory (Azure AD Connect), è possibile visualizzare il numero di telefono esaminando il parametro OnPremLineURi nell'output dal cmdlet [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) .

| Dove | Parametro | Valore |
| :------------| :-------| :---------|
| Active Directory locale | linea msRTCSIP | tel:+14255551234 |
| Microsoft 365 | OnPremLineURi | tel:+14255551234 |

### <a name="direct-routing-numbers-managed-in-microsoft-365"></a>Numeri di routing diretto gestiti in Microsoft 365

Se non gestisci i numeri di telefono direct routing nel Active Directory locale, questi vengono gestiti in Microsoft 365. Poiché i numeri di telefono non vengono sincronizzati con Microsoft 365, non sono visibili nel parametro OnPremLineUri nell'output del cmdlet Get-CsOnlineUser eseguito per l'account utente o della risorsa.

### <a name="direct-routing-numbers-managed-in-both-an-on-premises-active-directory-and-microsoft-365"></a>Numeri di routing diretto gestiti sia in un Active Directory locale che in Microsoft 365

È possibile gestire i numeri di telefono del routing diretto di alcuni account utente e risorse in un Active Directory locale e instradamento diretto dei numeri di telefono di altri account in Microsoft 365. Questa funzionalità dipende dal fatto che l'attributo msRTCSIP-Line sia impostato sull'account utente o risorsa nel Active Directory locale.    

### <a name="change-where-direct-routing-phone-numbers-are-managed"></a>Modificare la posizione in cui vengono gestiti i numeri di telefono per il routing diretto

Per modificare la posizione in cui viene gestito un numero di telefono per l'instradamento diretto, è necessario rimuovere il numero di telefono dall'attributo msRTCSIP-Line nell'account utente o della risorsa nel Active Directory locale.   

Per altre informazioni, vedere [Cancellare gli attributi di Skype for Business per tutti gli utenti locali in Active Directory](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory.md). Si noti che il numero di telefono deve essere riassegnati all'account utente o alla risorsa in Microsoft 365.

Dopo la sincronizzazione della rimozione con Microsoft 365, l'attributo OnPremLineUri nell'output da Get-CsOnlineUser sull'account utente o della risorsa sarà vuoto. 

