---
title: 'Lync Server 2013: assegnare un criterio di segreteria telefonica ospitata per utente'
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
ms.openlocfilehash: 95413733a9b23ce1f749ebb16521a3349b00165d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722956"
---
# <a name="assign-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a>Assegnare un criterio di segreteria telefonica ospitata per utente in Lync Server 2013

 


La distribuzione di uno o più criteri per la segreteria telefonica ospitata per utente è facoltativa. Se si distribuiscono criteri per utente, è necessario assegnarli esplicitamente a utenti, gruppi o oggetti contatto.

Per informazioni dettagliate sull'assegnazione o la rimozione dell'assegnazione di criteri per la segreteria telefonica ospitata per utente, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - Grant-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

## <a name="to-assign-a-per-user-hosted-voice-mail-policy"></a>Per assegnare un criterio di segreteria telefonica ospitata per utente

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet Grant-CsHostedVoicemailPolicy per assegnare i criteri di segreteria telefonica ospitata per utente a singoli utenti, gruppi e oggetti contatto. Ad esempio, eseguire:
    
        Grant-CsHostedVoicemailPolicy -Identity "Ken Myer" -PolicyName ExRedmond
    
    In questo esempio sono stati assegnati i criteri di segreteria telefonica ospitati da ExRedmond all'utente Ken.
    
    **Identity** specifica l'account utente da modificare. Il valore Identity può essere specificato usando uno dei formati seguenti:
    
      - Indirizzo SIP dell'utente
    
      - L'utente di Active Directory-Principal-Name dell'utente
    
      - Nome di accesso al\\dominio dell'utente (ad esempio,\\contoso kenmyer)
    
      - Il nome visualizzato dei servizi di dominio Active Directory dell'utente, ad esempio Ken. Se si usa il nome visualizzato come valore di identità, è possibile usare il carattere jolly\*asterisco (). Ad esempio, l'identità "\* Smith" restituisce tutti gli utenti che hanno un nome visualizzato che termina con il valore stringa "Smith".
    

    > [!NOTE]  
    > Il nome dell'account SAM di Active Directory dell'utente non può essere usato come valore di identità perché il nome dell'account SAM non è necessariamente univoco nella foresta.


