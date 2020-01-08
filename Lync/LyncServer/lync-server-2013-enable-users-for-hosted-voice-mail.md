---
title: 'Lync Server 2013: Abilitare gli utenti per la segreteria telefonica ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45872df26989d8d264ce77406bfbce86f321ccf8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a>Abilitare gli utenti per la segreteria telefonica ospitata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-24_

Seguire la procedura per abilitare gli utenti di Lync Server 2013 per la segreteria telefonica in un servizio di messaggistica unificata di Exchange ospitata.

Per informazioni dettagliate, vedere [gestione degli utenti di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) nella documentazione relativa alla pianificazione.

Per informazioni dettagliate sul cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) , vedere la documentazione di Lync Server Management Shell.

<div>


> [!IMPORTANT]  
> Prima che un utente di Lync Server 2013 possa essere abilitato per la segreteria telefonica ospitata, è necessario distribuire un criterio di segreteria telefonica ospitata che si applica al proprio account utente. Per informazioni dettagliate, vedere Criteri per la segreteria <A href="lync-server-2013-hosted-voice-mail-policies.md">telefonica ospitati in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a>Per abilitare gli utenti per la segreteria telefonica ospitata

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet Set-CsUser per configurare l'account utente per la segreteria telefonica ospitata. Ad esempio, eseguire:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    Nell'esempio precedente vengono impostati i parametri seguenti:
    
      - **HostedVoiceMail** consente alle chiamate di segreteria telefonica di un utente di essere indirizzate alla messaggistica unificata di Exchange ospitata. Segnala inoltre a Microsoft Lync 2013 di illuminare l'indicatore "chiama la segreteria telefonica".
    
      - **Identity** specifica l'account utente da modificare. Il valore Identity può essere specificato usando uno dei formati seguenti:
        
          - Indirizzo SIP dell'utente
        
          - L'utente di Active Directory-Principal-Name dell'utente
        
          - Nome di accesso al\\dominio dell'utente (ad esempio,\\contoso kenmyer)
        
          - Il nome visualizzato dei servizi di dominio Active Directory dell'utente, ad esempio Ken. Se si usa il nome visualizzato come valore di identità, è possibile usare il carattere jolly\*asterisco (). Ad esempio, l'identità "\* Smith" restituisce tutti gli utenti che hanno un nome visualizzato che termina con il valore stringa "Smith".
        
        <div>
        

        > [!NOTE]  
        > Il nome dell'account SAM di Active Directory dell'utente non può essere usato come valore di identità perché il nome dell'account SAM non è necessariamente univoco nella foresta.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

