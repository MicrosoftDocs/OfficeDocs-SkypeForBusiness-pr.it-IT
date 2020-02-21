---
title: 'Lync Server 2013: abilitare gli utenti per la segreteria telefonica ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 836edd026e6b80404b9a85a3d5a0f53fa2ba574a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Abilitare gli utenti per la segreteria telefonica ospitata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-24_

Seguire la procedura per abilitare gli utenti di Lync Server 2013 per la segreteria telefonica in un servizio di messaggistica unificata di Exchange ospitata.

Per ulteriori informazioni, vedere [gestione degli utenti di Exchange ospitati in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) nella documentazione relativa alla pianificazione.

Per informazioni dettagliate sul cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , vedere la documentazione di Lync Server Management Shell.

<div>


> [!IMPORTANT]  
> Prima che un utente di Lync Server 2013 possa essere abilitato per la segreteria telefonica ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata che si applica al proprio account utente. Per ulteriori informazioni, vedere <A href="lync-server-2013-hosted-voice-mail-policies.md">criteri di segreteria telefonica ospitata in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>Per abilitare gli utenti per la segreteria telefonica ospitata

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet Set-CsUser per configurare l'account utente per la segreteria telefonica ospitata. Ad esempio, eseguire:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    Nell'esempio precedente vengono impostati i parametri seguenti:
    
      - **HostedVoiceMail** consente di instradare le chiamate di posta vocale di un utente alla messaggistica unificata di Exchange ospitata. Segnala inoltre Microsoft Lync 2013 per accendere l'indicatore "segreteria telefonica chiamata".
    
      - **Identity** specifica l'account utente da modificare. Il valore di Identity può essere specificato utilizzando uno dei formati seguenti:
        
          - Indirizzo SIP dell'utente
        
          - Nome dell'entità utente di Active Directory
        
          - Nome di accesso del\\dominio dell'utente (ad esempio,\\contoso kenmyer)
        
          - Nome visualizzato dei servizi di dominio Active Directory dell'utente, ad esempio Davide Garghentini. Se si utilizza il nome visualizzato come valore Identity, è possibile utilizzare il carattere jolly asterisco\*(). Ad esempio, il parametro Identity\* "Smith" restituisce tutti gli utenti che dispongono di un nome visualizzato che termina con il valore stringa "Smith".
        
        <div>
        

        > [!NOTE]  
        > Il nome account SAM di Active Directory dell'utente non può essere utilizzato come valore di Identity perché non è necessariamente univoco nella foresta.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

