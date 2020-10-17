---
title: 'Lync Server 2013: assegnare un criterio di segreteria telefonica ospitata per utente'
description: 'Lync Server 2013: assegnare un criterio di segreteria telefonica ospitata per utente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user hosted voice mail policy
ms:assetid: d44c71a0-4407-4ab4-b7e0-d671dde3425f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398919(v=OCS.15)
ms:contentKeyID: 48185456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 071d504c452b4d3adb1b636cb5c4ff8835200107
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559892"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Assegnare criteri di segreteria telefonica ospitata per utente in Lync Server 2013

 


La distribuzione di uno o più criteri di segreteria telefonica ospitata per utente è facoltativa. Se si distribuiscono i criteri per utente, è necessario assegnarli in modo esplicito a utenti, gruppi o oggetti contatto.

Per informazioni dettagliate sull'assegnazione o la rimozione dell'assegnazione dei criteri di segreteria telefonica ospitata per utente, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>Per assegnare criteri di segreteria telefonica ospitata per utente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet Grant-CsHostedVoicemailPolicy per assegnare criteri di segreteria telefonica ospitata per utente a singoli utenti, gruppi e oggetti contatto. Ad esempio, eseguire:
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    In questo esempio il criterio ExRedmond è stato assegnato all'utente Davide Garghentini.
    
    **Identity** specifica l'account utente da modificare. Il valore di Identity può essere specificato utilizzando uno dei formati seguenti:
    
      - Indirizzo SIP dell'utente
    
      - Nome dell'entità utente di Active Directory
    
      - Nome di accesso del dominio dell'utente \\ (ad esempio, Contoso \\ kenmyer)
    
      - Nome visualizzato dei servizi di dominio Active Directory dell'utente, ad esempio Davide Garghentini. Se si utilizza il Display-Name come valore Identity, è possibile utilizzare il \* carattere jolly asterisco (). Ad esempio, il parametro Identity " \* Smith" restituisce tutti gli utenti che dispongono di un Display-Name che termina con il valore stringa "Smith".
    

    > [!NOTE]  
    > Il nome account SAM di Active Directory dell'utente non può essere utilizzato come valore di Identity perché non è necessariamente univoco nella foresta.


