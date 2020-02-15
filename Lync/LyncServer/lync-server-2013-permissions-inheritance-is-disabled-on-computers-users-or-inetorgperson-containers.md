---
title: "Lync Server 2013: l'ereditarietà delle autorizzazioni è disabilitata in computer, utenti o contenitori InetOrgPerson"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1340c76209667d705908f5012a8182eaf1c7c4cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>L'ereditarietà delle autorizzazioni è disabilitata su computer, utenti o contenitori InetOrgPerson in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-12-19_

In un servizio di dominio Active Directory bloccato, gli utenti e gli oggetti computer vengono spesso inseriti in unità organizzative specifiche con l'ereditarietà delle autorizzazioni disabilitata per proteggere la delega amministrativa e per abilitare l'utilizzo di oggetti Criteri di gruppo (GPO) per applicare i criteri di sicurezza.

Preparazione del dominio e attivazione del server impostare le voci di controllo di accesso (ACE) richieste da Lync Server 2013. Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza di Lync Server non possono ereditare tali ACE. Quando queste autorizzazioni non vengono ereditate, i gruppi di sicurezza di Lync Server non possono accedere alle impostazioni e si verificano i due problemi seguenti:

  - Per amministrare utenti, inetOrgPerson e contatti e per gestire i server, i gruppi di sicurezza di Lync Server richiedono gli ACE impostati dalla procedura di preparazione del dominio sui set di proprietà di ogni utente, l'RTC (Real-Time Communications), la ricerca degli utenti RTC e le informazioni pubbliche. . Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza non ereditano tali voci di controllo di accesso e non possono gestire né i server né gli utenti.

  - Per individuare i server e i pool, i server che eseguono Lync Server si basano sulle voci ACE impostate per l'attivazione su oggetti correlati al computer, tra cui il contenitore Microsoft e l'oggetto server. Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza, i server e i pool non ereditano tali voci di controllo di accesso e non possono usufruirne.

Per risolvere questi problemi, Lync Server fornisce il cmdlet **Grant-CsOUPermission** . Questo cmdlet imposta gli ACE di Lync Server necessari direttamente su un contenitore e unità organizzativa specificati e gli oggetti all'interno del contenitore o dell'unità organizzativa.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>Impostazione delle autorizzazioni per gli oggetti User, InetOrgPerson e Contact dopo l'esecuzione della preparazione del dominio

In un ambiente Active Directory bloccato in cui è disabilitata l'ereditarietà delle autorizzazioni, durante la preparazione del dominio non vengono impostate le voci di controllo di accesso necessarie nei contenitori o nelle unità organizzative che includono oggetti User o InetOrgPerson all'interno del dominio. In questa situazione, è necessario eseguire il cmdlet **Grant-CsOuPermission** in ogni contenitore o unità organizzativa con oggetti User o InetOrgPerson per cui è disabilitata l'ereditarietà delle autorizzazioni. Nel caso di una topologia a foresta centralizzata, è necessario eseguire questa procedura anche nei contenitori o nelle unità organizzative che contengono oggetti contatto. Per informazioni dettagliate sulle topologie di foreste centrali, vedere [supported Active Directory Topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) nella documentazione relativa alla supportabilità. Il parametro ObjectType specifica il tipo di oggetto. Il parametro OU specifica l'unità organizzativa.

Questo cmdlet consente di aggiungere le voci di controllo di accesso necessarie direttamente nei contenitori o nelle unità organizzative specificati e negli oggetti User o InetOrgPerson all'interno di tali contenitori. Se nell'unità organizzativa in cui viene eseguito il comando sono presenti le unità organizzative figlio con gli oggetti User o InetOrgPerson, le autorizzazioni non verranno applicate a tali utenti. Sarà necessario eseguire il comando su ogni unità organizzativa figlio individualmente. Si tratta di uno scenario comune con le distribuzioni di hosting di Lync, ad esempio, i tenant di OU = OCS, DC = CONTOSO, DC = LOCAL e Child OU = Tenant1, OU = OCS Tenants, DC = CONTOSO, DC = LOCAL.

Per eseguire questo cmdlet, è necessario disporre di diritti utente equivalenti all'appartenenza al gruppo Domain Admins. Se anche gli ACE degli utenti autenticati sono stati rimossi nell'ambiente bloccato, è necessario concedere a questo account le voci ACE di accesso in lettura nei contenitori o le unità organizzative rilevanti nel dominio radice della foresta, come descritto in [autorizzazioni utente autenticate sono state rimosse in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) oppure utilizzare un account membro del gruppo Enterprise Admins.

**Per impostare le voci di controllo di accesso necessarie per gli oggetti User, InetOrgPerson e Contact**

1.  Accedere a un computer appartenente al dominio con un account membro del gruppo Domain Admins o che disponga di diritti utente equivalenti.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.
    
    Ad esempio:
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  Nel file di registro, cercare il risultato dell'esecuzione di ** \<esito positivo\> ** alla fine di ogni attività per verificare che le autorizzazioni siano state impostate e quindi chiudere la finestra del registro. In alternativa, è possibile eseguire il comando seguente per determinare se le autorizzazioni sono state impostate:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Ad esempio:
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>Impostazione delle autorizzazioni per oggetti Computer dopo l'esecuzione della preparazione del dominio

In un ambiente Active Directory bloccato in cui è disabilitata l'ereditarietà delle autorizzazioni, durante la preparazione del dominio non vengono impostate le voci di controllo di accesso necessarie nei contenitori o nelle unità organizzative che includono oggetti Computer all'interno del dominio. In questo caso, è necessario eseguire il cmdlet **Grant-CsOUPermission** in ogni contenitore o unità organizzativa che dispone di computer che eseguono Lync Server in cui l'ereditarietà delle autorizzazioni è disabilitata. Il parametro ObjectType specifica il tipo di oggetto.

Questa procedura consente di aggiungere le voci di controllo di accesso necessarie direttamente nei contenitori specificati.

Per eseguire questo cmdlet, è necessario disporre di diritti utente equivalenti all'appartenenza al gruppo Domain Admins. Se anche gli ACE degli utenti autenticati sono stati rimossi, è necessario concedere questo account alle voci ACE di accesso in lettura nei contenitori rilevanti nel dominio radice della foresta, come descritto in [autorizzazioni utente autenticate sono state rimosse in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) oppure utilizzare un account membro del gruppo Enterprise Admins.

**Per impostare le voci di controllo di accesso necessarie per gli oggetti computer**

1.  Accedere al computer del dominio con un account membro del gruppo Domain Admins o che disponga di diritti utente equivalenti.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.
    
    Ad esempio:
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  Nel file di registro di esempio C\\:\\logs OUPermissions. XML, è necessario cercare il risultato dell'esecuzione di ** \<esito positivo\> ** alla fine di ogni attività e verificare che non vi siano errori e quindi chiudere il registro. È possibile eseguire il cmdlet seguente per verificare le autorizzazioni:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Ad esempio:
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > Se si esegue la preparazione del dominio nel dominio radice della foresta in un ambiente Active Directory bloccato, tenere presente che Lync Server richiede l'accesso ai contenitori dello schema e della configurazione di Active Directory.<BR>Se l'autorizzazione utente autenticata predefinita è stata rimossa dallo schema o dai contenitori di configurazione&nbsp;in servizi di dominio Active Directory, solo i membri del gruppo Schema Admins (per il contenitore dello schema) o del gruppo Enterprise Admins (per il contenitore di configurazione) sono autorizzati ad accedere al contenitore specificato. Poiché Setup. exe, i cmdlet di Lync Server Management Shell e il pannello di controllo di Lync Server richiedono l'accesso a questi contenitori, l'installazione e l'installazione degli strumenti di amministrazione avranno esito negativo a meno che l'utente che esegue l'installazione disponga di diritti utente equivalenti allo schema. Appartenenza ai gruppi Admins e Enterprise Admins.<BR>Per risolvere questo problema, sarà necessario concedere al gruppo RTCUniversalGlobalWriteGroup l'accesso in lettura e scrittura ai contenitori dello schema e della configurazione.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

