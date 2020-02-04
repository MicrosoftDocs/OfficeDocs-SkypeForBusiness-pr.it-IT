---
title: 'Lync Server 2013: Creare oggetti contatto per la messaggistica unificata di Exchange ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 358b595fceb05a377c59479b0a08e100bffb318a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Creare oggetti contatto per la messaggistica unificata di Exchange ospitata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-24_

La procedura seguente illustra come creare oggetti contatto di operatore automatico (AA) o di accesso sottoscrittore per la messaggistica unificata di Exchange ospitata.

Per informazioni dettagliate, vedere [gestione degli oggetti contatto di Exchange ospitati in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) nella documentazione relativa alla pianificazione.

Per informazioni dettagliate sulla configurazione degli oggetti contatto, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Prima che gli oggetti contatto di Lync Server 2013 possano essere abilitati per la messaggistica unificata di Exchange ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata. Per informazioni dettagliate, vedere Criteri per la segreteria <A href="lync-server-2013-hosted-voice-mail-policies.md">telefonica ospitati in Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>Per creare oggetti contatto AA o SA per la messaggistica unificata di Exchange ospitata

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsExUmContact per creare qualsiasi oggetto contatto necessario per la distribuzione. Ad esempio, Esegui le operazioni seguenti per creare un oggetto contatto AA e SA:
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    In questi esempi vengono impostati i parametri seguenti:
    
      - **SipAddress** specifica l'indirizzo SIP dell'oggetto contatto. Deve essere un indirizzo che non è già stato usato per configurare un utente o un oggetto contatto in servizi di dominio Active Directory. Questo valore deve essere nel formato "SIP:\<*SIP Address*\>", come illustrato negli esempi precedenti.
    
      - **RegistrarPool** specifica il nome di dominio completo (FQDN) del pool in cui è in uso il servizio registrar.
        
        <div class=" ">
        

        > [!NOTE]  
        > Gli oggetti contatto di messaggistica unificata di Exchange non possono essere spostati nei pool che fanno parte delle distribuzioni di Lync Server 2013 prima di Lync Server 2013.

        
        </div>
    
      - **Ou** specifica l'unità organizzativa Active Directory in cui verrà individuato l'oggetto contatto.
    
      - **DisplayNumber** specifica il numero di telefono dell'oggetto contatto. Il numero di telefono per ogni oggetto contatto deve essere univoco.
    
      - **AutoAttendant specifica se** l'oggetto contatto è un operatore automatico. Operatore automatico fornisce un set di richieste vocali che consentono ai chiamanti di spostarsi nel sistema telefonico e di raggiungere l'interlocutore che vuole contattare. Il valore **false** (impostazione predefinita) per questo parametro indica un oggetto contatto di accesso del Sottoscrittore.

</div>

</div>

<span> </span>

</div>

</div>

</div>

