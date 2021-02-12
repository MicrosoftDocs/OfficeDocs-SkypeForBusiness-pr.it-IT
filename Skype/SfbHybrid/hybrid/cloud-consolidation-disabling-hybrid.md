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
description: Questa appendice include la procedura dettagliata per disabilitare l'ambiente ibrido come parte del consolidamento del cloud per Teams e Skype for Business.
ms.openlocfilehash: 93aad1ea230d9edbb81673a3ddabc7088b06d422
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277253"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>Disabilitare la soluzione ibrida per completare la migrazione al cloud

Dopo aver spostato tutti gli utenti dall'infrastruttura locale al cloud, è possibile ritirare la distribuzione locale di Skype for Business. Oltre a rimuovere qualsiasi hardware, un passaggio critico consiste nel separare logicamente la distribuzione locale da Microsoft 365 o Office 365 disabilitando l'ambiente ibrido. La disabilitazione ibrida è costituita da 3 passaggi:

1. Aggiornare i record DNS in modo che puntino a Microsoft 365 o Office 365.

2. Disabilitare il dominio diviso nell'organizzazione di Microsoft 365 o Office 365.

3. Disabilitare la possibilità in locale di comunicare con Microsoft 365 o Office 365.

Questi passaggi devono essere evasi insieme come un'unità. I dettagli sono forniti di seguito. Vengono inoltre fornite linee guida per la gestione dei numeri di telefono per gli utenti migrati dopo la disconnessione della distribuzione locale.

Una volta completati questi passaggi, i server Skype for Business locali non vengono più utilizzati e questi server possono essere nuovamente immagineti.

> [!Important] 
>È consigliabile continuare a consentire la sincronizzazione degli attributi msRTCSIP in Active Directory tramite Azure AD Connect in Azure AD.  Non cancellare nessuno di questi attributi, a meno che non sia indicato dal supporto.  Non eseguire Disable-CsUser nell'ambiente locale. Se è necessario modificare l'indirizzo SIP di un utente, eseguire questa operazione in Active Directory locale e consentire la sincronizzazione delle modifiche in Azure AD tramite Azure AD Connect, come descritto di seguito. Analogamente, se è necessario modificare un numero di telefono e lineURI dell'utente è già definito in locale, è necessario modificarlo in Active Directory locale.
>La cancellazione degli attributi msRTCSIP locali dopo la migrazione dall'ambiente locale può comportare la perdita di servizio per gli utenti.


1.  *Aggiornare DNS in modo che punti a Microsoft 365 o Office 365.*
Il DNS esterno dell'organizzazione per l'organizzazione locale deve essere aggiornato in modo che i record skype for business puntino a Microsoft 365 o Office 365 anziché alla distribuzione locale. In particolare:

    |Tipo di record|Nome|TTL|Value|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|
    |CNAME| meet|   3600|   webdir.online.lync. <span> com|
    |CNAME| dialin  |3600|  webdir.online.lync. <span> com|

    È inoltre possibile eliminare i record CNAME per meet o dialin (se presenti). Infine, tutti i record DNS per Skype for Business nella rete interna devono essere rimossi.

    > [!Note] 
    > In rari casi, la modifica del DNS dall'puntare in locale a Office 365 per l'organizzazione può causare la federazione con altre organizzazioni smettere di funzionare finché l'altra organizzazione non aggiorna la configurazione della federazione:
    >
    > - Tutte le organizzazioni federate che utilizzano il modello di federazione diretta meno recente (noto anche come Server partner consentito) dovranno aggiornare le voci di dominio consentite per l'organizzazione per rimuovere il nome di dominio completo del proxy. Questo modello di federazione legacy non è basato sui record DNS SRV, quindi una configurazione di questo tipo diventerà non aggiornata una volta che l'organizzazione si sposta nel cloud.
    > 
    > - Qualsiasi organizzazione federata che non dispone di un provider di hosting abilitato per sipfed.online.lync. <span> com dovrà aggiornare la configurazione per abilitarla. Questa situazione è possibile solo se l'organizzazione federata è puramente locale e non ha mai federato un tenant ibrido o online. In tal caso, la federazione con queste organizzazioni non funzionerà finché non abilita il provider di hosting.
    >
    > Se si sospetta che uno dei partner federati utilizzi la federazione diretta o che non abbia federato un'organizzazione online o ibrida, è consigliabile inviare loro una comunicazione al riguardo mentre si prepara a completare la migrazione al cloud.


2.  *Disabilitare lo spazio di indirizzi SIP condiviso nell'organizzazione di Microsoft 365 o Office 365.*
Il comando seguente deve essere eseguito da una finestra di PowerShell di Skype for Business online.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Disabilitare la possibilità in locale di comunicare con Microsoft 365 o Office 365.*  
Il comando seguente deve essere eseguito da una finestra di PowerShell locale:

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>Gestire gli indirizzi SIP e i numeri di telefono per gli utenti migrati dall'ambiente locale

Gli amministratori possono gestire gli utenti che in precedenza erano stati spostati da Skype for Business Server locale al cloud, anche dopo la rimozione della distribuzione locale. Se si desidera apportare modifiche all'indirizzo SIP di un utente o all'URI di linea di un utente (e l'indirizzo SIP o l'URI linea è già definito in Active Directory locale), è necessario eseguire questa operazione in Active Directory locale e consentire il flusso dei valori fino ad Azure AD. Ciò NON richiede Skype for Business Server locale. È invece possibile modificare questi attributi direttamente in Active Directory locale, utilizzando lo snap-in MMC Utenti e computer di Active Directory o PowerShell. Se si utilizza lo snap-in MMC, aprire la pagina delle proprietà dell'utente, fare clic sulla scheda Editor attributi e individuare gli attributi appropriati da modificare:

- Per modificare l'indirizzo SIP di un utente, modificare il `msRTCSIP-PrimaryUserAddress` parametro . Inoltre, se l'attributo contiene un valore SIP, aggiornare tale valore SIP in modo che `ProxyAddresses` corrisponda al nuovo valore di `msRTCSIP-PrimaryUserAddress` . Se non contiene un valore SIP, è possibile lasciarlo vuoto.

- Per modificare il numero di telefono di un utente, modificare `msRTCSIP-Line` *se ha già un valore.*

  ![Strumento Utenti e computer di Active Directory](../media/disable-hybrid-1.png)
  
Se l'utente originariamente non aveva un valore per l'ambiente locale prima dello spostamento, è possibile modificare il lineURI utilizzando il parametro - nel `LineURI` `onpremLineUri` cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) nel modulo PowerShell di Skype for Business online.


## <a name="see-also"></a>Vedere anche

[Consolidamento del cloud per Teams e Skype for Business](cloud-consolidation.md)
