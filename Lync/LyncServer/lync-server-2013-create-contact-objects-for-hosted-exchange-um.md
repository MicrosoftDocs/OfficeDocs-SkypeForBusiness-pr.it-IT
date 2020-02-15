---
title: 'Lync Server 2013: creare gli oggetti contatto per la messaggistica unificata di Exchange ospitata'
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
ms.openlocfilehash: 15a238c2517fd295d35d63a8a1d2f4c4e88a76b4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a>Creare oggetti contatto per la messaggistica unificata di Exchange ospitata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-24_

Nella procedura riportata di seguito viene illustrato come creare oggetti contatto Operatore automatico o Accesso sottoscrittore per la messaggistica unificata di Exchange ospitata.

Per ulteriori informazioni, vedere [gestione degli oggetti contatto di Exchange ospitati in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) nella documentazione relativa alla pianificazione.

Per informazioni dettagliate sulla configurazione degli oggetti contatto, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - [New-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [Set-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> Prima di poter abilitare gli oggetti contatto di Lync Server 2013 per la messaggistica unificata di Exchange ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata. Per ulteriori informazioni, vedere <A href="lync-server-2013-hosted-voice-mail-policies.md">criteri di segreteria telefonica ospitata in Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a>Per creare oggetti contatto Operatore automatico o Accesso sottoscrittore per la messaggistica unificata di Exchange ospitata

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsExUmContact per creare gli oggetti contatto necessari per la distribuzione. Ad esempio, per creare un oggetto contatto Operatore automatico e un oggetto contatto Accesso sottoscrittore:
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    In questi esempi vengono impostati i parametri seguenti:
    
      - **SipAddress** specifica l'indirizzo SIP dell'oggetto contatto. Deve corrispondere a un indirizzo non ancora utilizzato per la configurazione di un utente o di un oggetto contatto in Servizi di dominio Active Directory. Questo valore deve essere nel formato "SIP:\<*SIP Address*\>", come illustrato negli esempi precedenti.
    
      - **RegistrarPool** specifica il nome di dominio completo (FQDN) del pool su cui è in esecuzione il servizio di registrazione.
        
        <div class=" ">
        

        > [!NOTE]  
        > Gli oggetti contatto di messaggistica unificata di Exchange non possono essere spostati nei pool che fanno parte delle distribuzioni di Lync Server 2013 precedenti a Lync Server 2013.

        
        </div>
    
      - **OU** specifica l'unità organizzativa Active Directory in cui sarà situato l'oggetto contatto.
    
      - **DisplayNumber** specifica il numero di telefono dell'oggetto contatto. Il numero di telefono deve essere univoco per ogni oggetto contatto.
    
      - **AutoAttendant** specifica se l'oggetto contatto è un operatore automatico. La funzionalità Operatore automatico mette a disposizione una serie di istruzioni vocali che consentono ai chiamanti di navigare nel sistema telefonico fino a raggiungere l'interlocutore desiderato. Per questo parametro il valore **$False** (predefinito) indica un oggetto contatto Accesso sottoscrittore.

</div>

</div>

<span> </span>

</div>

</div>

</div>

