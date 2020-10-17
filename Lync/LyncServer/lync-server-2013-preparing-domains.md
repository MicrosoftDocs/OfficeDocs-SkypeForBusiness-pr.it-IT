---
title: 'Lync Server 2013: preparazione di domini'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a37c365732785198e45a546f2352c51ccb42f9dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506943"
---
# <a name="preparing-domains-for-lync-server-2013"></a>Preparazione dei domini per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-29_

La preparazione del dominio è il passaggio finale nella preparazione di servizi di dominio Active Directory per Lync Server 2013. Questa operazione comporta l'aggiunta delle voci di controllo di accesso necessarie ai gruppi universali che concedono autorizzazioni per ospitare e gestire gli utenti nell'ambito del dominio. Con la preparazione del dominio vengono create voci di controllo di accesso nella radice del dominio e tre contenitori predefiniti per utenti, computer e controller di dominio.

È possibile eseguire la preparazione del dominio in qualsiasi computer del dominio in cui si distribuisce Lync Server. È necessario preparare tutti i domini che ospiteranno Lync Server o gli utenti.

Se l'ereditarietà delle autorizzazioni è disabilitata o le autorizzazioni degli utenti autenticati sono disabilitate nell'organizzazione, durante la preparazione del dominio sono necessari alcuni passaggi aggiuntivi. Per ulteriori informazioni, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

Se nell'organizzazione vengono utilizzate unità organizzative anziché i tre contenitori predefiniti, ovvero Utenti, Computer e Controller di dominio, sarà necessario concedere al gruppo Authenticated Users l'accesso in lettura alle unità organizzative. L'accesso in lettura ai contenitori è necessario per la preparazione del dominio. Se il gruppo Utenti autenticati non dispone di accesso in lettura all'unità organizzativa, eseguire il cmdlet **Grant-CsOuPermission** come illustrato negli esempi di codice seguenti per concedere l'autorizzazione di lettura per ogni unità organizzativa.

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

Per informazioni dettagliate sul cmdlet **Grant-CsOUPermission** , vedere la documentazione di Lync Server Management Shell.

<div class="">


> [!TIP]  
> Per informazioni dettagliate sulle voci di controllo di accesso create nella radice del dominio e nei contenitori utenti, computer e controller di dominio, vedere <A href="lync-server-2013-changes-made-by-domain-preparation.md">changes made by domain preparation in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Esecuzione della preparazione del dominio per Lync Server 2013](lync-server-2013-running-domain-preparation.md)

  - [Utilizzo dei cmdlet per annullare la preparazione del dominio per Lync Server 2013](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

