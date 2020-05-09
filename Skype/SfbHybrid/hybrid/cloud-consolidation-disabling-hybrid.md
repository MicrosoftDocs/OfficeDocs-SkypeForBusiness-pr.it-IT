---
title: Disabilitare la soluzione ibrida per completare la migrazione al cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: In questa appendice sono riportati i passaggi dettagliati per la disabilitazione dell'ibrido come parte del consolidamento cloud per Teams e Skype for business.
ms.openlocfilehash: c6d042095298f6cab8d9474a521b9362ece13e0d
ms.sourcegitcommit: 0dda90122769385529f78f70b0467848da97e5ec
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173972"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Disabilitare la soluzione ibrida per completare la migrazione al cloud

Dopo aver spostato tutti gli utenti dall'infrastruttura locale al cloud, è possibile ritirare la distribuzione locale di Skype for Business. Oltre a rimuovere eventuale hardware, un passaggio critico è quello di separare logicamente la distribuzione locale da Office 365 disabilitando l'ambiente ibrido. La disattivazione dell'ibrido è costituita da tre passaggi:

- Aggiornare i record NS in modo che puntino a Office 365.
- Disabilitare il dominio diviso nell'organizzazione di Office 365.
- Disabilitare l'abilità in locale per comunicare con Office 365.

Questi passaggi devono essere eseguiti insieme come unità. I dettagli sono riportati di seguito. Inoltre, vengono fornite linee guida per la gestione dei numeri di telefono per gli utenti migrati dopo che la distribuzione locale è stata disconnessa.

> [!Important] 
>È consigliabile continuare a lasciare che gli attributi msRTCSIP in Active Directory vengano sincronizzati tramite Azure AD Connect in Azure AD.  Non cancellare nessuno di questi attributi, a meno che non venga diretto dal supporto.  Non eseguire Disable-CsUser nell'ambiente locale. Se è necessario modificare l'indirizzo SIP di un utente, eseguirlo in Active Directory locale e lasciare che questa modifica venga sincronizzata in Azure AD tramite Azure AD Connect come descritto di seguito. Analogamente, se è necessario modificare un numero di telefono e il LineURI dell'utente è già definito in locale, è necessario modificarlo in Active Directory locale.
>La cancellazione degli attributi msRTCSIP locali dopo la migrazione da locale può comportare la perdita del servizio per gli utenti.



1.  *Aggiornare il DNS in modo che punti a Office 365.*
I record DNS esterni esistenti dell'organizzazione per l'organizzazione locale devono essere aggiornati in modo che i record Skype for business puntino a Office 365 anziché alla distribuzione locale. In particolare:

    |Tipo di record|Nome|TTL|Valore|Scopo|
    |---|---|---|---|---|
    |SRV|_sipfederationtls. _tcp|3600|100 1 5061 sipfed. online. Lync. <span>com|Abilita la Federazione|
    |SRV|_sip. _tls|3600|100 1 443 sipdir. online. Lync. <span>com|Obbligatorio per gli utenti di Skype for business|
    |CNAME| lyncdiscover|   3600|   WEBDIR. online. Lync. <span>com|Obbligatorio per gli utenti di Skype for business|
    |CNAME| sip|    3600|   sipdir. online. Lync. <span>com|Necessario solo per i telefoni SIP legacy meno recenti|

    È inoltre possibile eliminare i record CNAME per Meet o dialin (se presente).

    > [!Note] 
    > In rari casi, la modifica del DNS dal punto di vista locale a Office 365 per l'organizzazione può causare la Federazione con alcune altre organizzazioni di smettere di funzionare fino a quando l'altra organizzazione non aggiorna la configurazione della Federazione:
    >
    > - Qualsiasi organizzazione federata che utilizza il modello di Federazione diretto meno recente (noto anche come server partner consentito) dovrà aggiornare le voci di dominio consentite per la propria azienda per rimuovere il nome FQDN del proxy. Questo modello di federazione legacy non è basato sui record DNS SRV, quindi tale configurazione diventerà obsoleta dopo lo spostamento dell'organizzazione nel cloud.
    > 
    > - Qualsiasi organizzazione federata che non disponga di un provider di hosting abilitato per sipfed. online. Lync. <span>com sarà necessario aggiornare la propria configurazione per abilitarlo. Questa situazione è possibile solo se l'organizzazione federata è puramente locale e non è mai stata federata con nessun tenant ibrido o online. In tal caso, la Federazione con queste organizzazioni non funzionerà finché non Abilita il proprio provider di hosting.
    >
    > Se si sospetta che uno qualsiasi dei partner federati possa utilizzare la Federazione diretta o che non sia stato federato con nessuna organizzazione online o ibrida, è consigliabile inviare loro una comunicazione durante la preparazione per completare la migrazione nel cloud.

2.  *Disabilitare lo spazio degli indirizzi SIP condiviso nell'organizzazione di Office 365.*
Il comando seguente deve essere effettuato da una finestra di PowerShell di Skype for business online.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Disabilitare l'abilità in locale per comunicare con Office 365.*  
Il comando seguente deve essere effettuato da una finestra di PowerShell locale:

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Gestire gli indirizzi SIP e i numeri di telefono per gli utenti migrati da locale

Gli amministratori possono gestire gli utenti precedentemente spostati da un server Skype for business locale al cloud, anche dopo che la distribuzione locale è stata disattivata. Se si desidera apportare modifiche all'indirizzo SIP di un utente o all'URI di linea di un utente (e l'indirizzo SIP o l'URI della linea è già definito in Active Directory locale), è necessario eseguire questa operazione in Active Directory locale e lasciare che il valore o i valori vengano convogliati fino a Azure AD. Questo non richiede Skype for Business Server locale. È invece possibile modificare questi attributi direttamente in Active Directory locale, utilizzando lo snap-in MMC utenti e computer di Active Directory o tramite PowerShell. Se si utilizza lo snap-in MMC, aprire la pagina delle proprietà dell'utente, fare clic sulla scheda Attribute Editor e trovare gli attributi corretti da modificare:

- Per modificare l'indirizzo SIP di un utente, modificare `msRTCSIP-PrimaryUserAddress`il. Inoltre, se l' `ProxyAddresses` attributo contiene un valore SIP, aggiornare il valore SIP in modo che corrisponda al nuovo `msRTCSIP-PrimaryUserAddress`valore di. Se non contiene un valore SIP, è possibile lasciarlo vuoto.

- Per modificare il numero di telefono di un utente `msRTCSIP-Line` , modificare *se è già presente un valore*.

  ![Strumento utenti e computer di Active Directory](../media/disable-hybrid-1.png)
  
Se l'utente non ha originariamente un valore per `LineURI` l'ambiente locale prima dello spostamento, è possibile modificare LineURI utilizzando il parametro-`onpremLineUri` nel [cmdlet Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) nel modulo di PowerShell di Skype for business online.


## <a name="see-also"></a>Vedere anche

[Consolidamento cloud per Teams e Skype for business](cloud-consolidation.md)
