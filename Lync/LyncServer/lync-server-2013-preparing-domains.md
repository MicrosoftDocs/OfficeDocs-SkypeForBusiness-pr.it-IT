---
title: 'Lync Server 2013: Preparazione dei domini'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cd8c09346c8f5b562a72e77b9ba40915b480c91
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>Preparazione dei domini per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-29_

La preparazione del dominio è il passaggio finale della preparazione dei servizi di dominio Active Directory per Lync Server 2013. Il passaggio preparazione del dominio aggiunge le voci di controllo di accesso (ACE) necessarie ai gruppi universali che assegnano le autorizzazioni per ospitare e gestire gli utenti all'interno del dominio. La preparazione del dominio crea ACE nella radice del dominio e tre contenitori predefiniti: User, computer e Domain controller.

È possibile eseguire la preparazione del dominio in qualsiasi computer del dominio in cui si sta distribuendo Lync Server. È necessario preparare ogni dominio che ospiterà Lync Server o gli utenti.

Se l'ereditarietà delle autorizzazioni è disabilitata o le autorizzazioni dell'utente autenticate sono disabilitate nell'organizzazione, è necessario eseguire ulteriori passaggi durante la preparazione del dominio. Per informazioni dettagliate, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Se l'organizzazione USA unità organizzative (OU) anziché i tre contenitori predefiniti, ovvero utenti, computer e controller di dominio, è necessario concedere l'accesso in lettura alle unità organizzative per il gruppo Authenticated Users. Per la preparazione del dominio è necessaria l'accesso in lettura ai contenitori. Se il gruppo Authenticated Users non ha accesso in lettura all'unità organizzativa, eseguire il cmdlet **Grant-CsOUPermission** come illustrato negli esempi di codice seguenti per concedere le autorizzazioni di lettura per ogni ou.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

Per informazioni dettagliate sul cmdlet **Grant-CsOUPermission** , vedere la documentazione di Lync Server Management Shell.

<div class="">


> [!TIP]  
> Per informazioni dettagliate sulle voci ACE create nella radice del dominio e nei contenitori utenti, computer e controller di dominio, vedere <A href="lync-server-2013-changes-made-by-domain-preparation.md">modifiche apportate dalla preparazione del dominio in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Esecuzione della preparazione del dominio per Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Utilizzo di cmdlet per ripristinare la preparazione del dominio per Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

