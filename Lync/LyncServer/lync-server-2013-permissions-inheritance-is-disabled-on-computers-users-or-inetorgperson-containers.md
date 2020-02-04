---
title: 'Lync Server 2013: Ereditarietà delle autorizzazioni disabilitata nei contenitori di oggetti Computer, User o InetOrgPerson'
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
ms.openlocfilehash: da84454a6e02e02520206b5eb667edfcf4fce849
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>Ereditarietà delle autorizzazioni disabilitata nei contenitori di oggetti Computer, User o InetOrgPerson in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-12-19_

In un servizio di dominio Active Directory bloccato, gli utenti e gli oggetti computer vengono spesso collocati in unità organizzative specifiche con l'ereditarietà delle autorizzazioni disabilitata per proteggere la delega amministrativa e per consentire l'uso di oggetti Criteri di gruppo (GPO) per applicare i criteri di sicurezza.

Preparazione del dominio e attivazione del server impostare le voci di controllo di accesso (ACE) richieste da Lync Server 2013. Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza di Lync Server non possono ereditare le voci ACE. Quando queste autorizzazioni non vengono ereditate, i gruppi di sicurezza di Lync Server non possono accedere alle impostazioni e sorgono i due problemi seguenti:

  - Per amministrare utenti, inetOrgPerson e contatti e per gestire i server, i gruppi di sicurezza di Lync Server richiedono gli ACE impostati dalla procedura di preparazione del dominio sui set di proprietà di ogni utente, le comunicazioni in tempo reale (RTC), la ricerca degli utenti RTC e le informazioni pubbliche . Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza non ereditano queste Ace e non possono gestire server o utenti.

  - Per individuare server e pool, i server che utilizzano Lync Server si basano sulle voci ACE impostate per l'attivazione in oggetti correlati al computer, incluso il contenitore Microsoft e l'oggetto server. Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza, i server e i pool non ereditano queste voci ACE e non possono sfruttare queste voci ACE.

Per risolvere questi problemi, Lync Server fornisce il cmdlet **Grant-CsOUPermission** . Questo cmdlet imposta le voci ACE di Lync Server necessarie direttamente su un contenitore e le unità organizzative specificati e gli oggetti all'interno del contenitore o dell'unità organizzativa.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>Impostare le autorizzazioni per gli oggetti utente, InetOrgPerson e contatto dopo l'uso della preparazione del dominio

In un ambiente Active Directory bloccato in cui l'ereditarietà delle autorizzazioni è disabilitata, la preparazione del dominio non imposta le voci ACE necessarie per i contenitori o le unità organizzative che tengono gli utenti o gli oggetti InetOrgPerson all'interno del dominio. In questo caso, è necessario eseguire il cmdlet **Grant-CsOUPermission** in ogni contenitore o ou che contiene oggetti utente o inetOrgPerson per cui l'ereditarietà delle autorizzazioni è disabilitata. Se si ha una topologia di foresta centrale, è necessario eseguire questa procedura anche per i contenitori o le unità organizzative che contengono oggetti contatto. Per informazioni dettagliate sulle topologie della foresta centrale, vedere [topologie di Active Directory supportate in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) nella documentazione relativa alla supportabilità. Il parametro ObjectType specifica il tipo di oggetto. Il parametro OU specifica l'unità organizzativa.

Questo cmdlet aggiunge le voci ACE necessarie direttamente ai contenitori o alle unità organizzative specificate e agli oggetti utente o InetOrgPerson all'interno del contenitore. Se l'unità organizzativa in cui viene eseguito il comando include unità organizzative figlio con oggetti utente o InetOrgPerson, le autorizzazioni non verranno applicate in tali. Sarà necessario eseguire il comando su ogni unità organizzativa figlio individualmente. Si tratta di uno scenario comune con le distribuzioni di hosting di Lync, ad esempio i tenant di OU = OCS, DC = CONTOSO, DC = LOCAL e Child OU = Tenant1, OU = OCS tenant, DC = CONTOSO, DC = LOCAL.

Per eseguire questo cmdlet sono necessari diritti utente equivalenti all'appartenenza al gruppo Domain Admins. Se le voci ACE dell'utente autenticato sono state rimosse anche nell'ambiente bloccato, è necessario concedere l'account ACEs di accesso in lettura per i contenitori o le unità organizzative del dominio radice della foresta, come descritto in [autorizzazioni utente autenticate vengono rimosse in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o usare un account membro del gruppo amministratori organizzazione.

**Per impostare le voci ACE obbligatorie per gli oggetti utente, InetOrgPerson e contatto**

1.  Accedere a un computer collegato al dominio con un account membro del gruppo Domain Admins o con diritti utente equivalenti.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.
    
    Ad esempio:
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  Nel file di log cercare il risultato dell'esecuzione di ** \<successo\> ** alla fine di ogni attività per verificare che le autorizzazioni siano state impostate e quindi chiudere la finestra del log. In alternativa, è possibile eseguire il comando seguente per determinare se sono state impostate le autorizzazioni:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Ad esempio:
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>Impostare le autorizzazioni per gli oggetti computer dopo aver eseguito la preparazione del dominio

In un ambiente Active Directory bloccato in cui l'ereditarietà delle autorizzazioni è disabilitata, la preparazione del dominio non imposta le voci ACE necessarie per i contenitori o le unità organizzative che contengono oggetti computer all'interno del dominio. In questo caso, è necessario eseguire il cmdlet **Grant-CsOUPermission** in ogni contenitore o ou che include computer che eseguono Lync Server in cui l'ereditarietà delle autorizzazioni è disabilitata. Il parametro ObjectType specifica il tipo di oggetto.

Questa procedura aggiunge le voci ACE necessarie direttamente nei contenitori specificati.

Per eseguire questo cmdlet sono necessari diritti utente equivalenti all'appartenenza al gruppo Domain Admins. Se sono state rimosse anche le voci ACE dell'utente autenticato, è necessario concedere a questo account le voci ACE di accesso in lettura nei contenitori rilevanti nel dominio radice della foresta, come descritto in [autorizzazioni utente autenticate vengono rimosse in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o usare un account membro del gruppo amministratori organizzazione.

**Per impostare le voci ACE obbligatorie per gli oggetti computer**

1.  Accedere al computer del dominio con un account membro del gruppo Domain Admins o con diritti utente equivalenti.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.
    
    Ad esempio:
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  Nel file di log di esempio C\\:\\logs OUPermissions. XML, si cercherà il risultato dell'esecuzione di ** \<successo\> ** alla fine di ogni attività e verificare che non ci siano errori e quindi chiudere il log. Puoi eseguire il cmdlet seguente per testare le autorizzazioni:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Ad esempio:
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > Se si esegue la preparazione del dominio nel dominio radice della foresta in un ambiente Active Directory bloccato, tenere presente che Lync Server richiede l'accesso ai contenitori dello schema e della configurazione di Active Directory.<BR>Se l'autorizzazione utente autenticata predefinita viene rimossa dallo schema o dai contenitori di configurazione in&nbsp;servizi di dominio Active Directory, solo i membri del gruppo amministratori schema (per il contenitore dello schema) o del gruppo amministratori organizzazione (per il contenitore di configurazione) possono accedere al contenitore indicato. Poiché Setup. exe, i cmdlet di Lync Server Management Shell e il pannello di controllo di Lync Server richiedono l'accesso a questi contenitori, la configurazione e l'installazione degli strumenti di amministrazione avranno esito negativo, a meno che l'utente che ha eseguito l'installazione abbia diritti utente equivalenti a schema Membri del gruppo amministratori e amministratori aziendali.<BR>Per risolvere il problema, è necessario concedere l'accesso in lettura e scrittura del gruppo RTCUniversalGlobalWriteGroup ai contenitori schema e configurazione.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

