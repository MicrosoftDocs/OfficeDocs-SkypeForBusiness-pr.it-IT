---
title: Modificare l'azione predefinita per i client non supportati in modo esplicito o con restrizioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87f2b88b43c41a5a8bf990a72f0fdfef1c5537e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Modificare l'azione predefinita per i client non supportati in modo esplicito o con restrizioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Oltre a specificare la versione dei client che si desidera supportare nell'ambiente Lync Server 2013, è anche possibile specificare un'azione predefinita per i client che non dispongono già di un criterio di versione definito. In questo modo è possibile limitare le versioni client utilizzate nell'ambiente Lync Server, che consentono di controllare i costi associati al supporto di più versioni client.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>Per modificare l'azione predefinita per i client non supportati in modo esplicito o con restrizioni

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra spostamento sinistra fare clic su **Client** e quindi su **Configurazione versione client**.

4.  Nella pagina **Configurazione versione client** fare doppio clic sulla configurazione **Globale** nell'elenco.

5.  Nella finestra di dialogo **Modifica Configurazione versione client** verificare che la casella di controllo **Abilita controllo versione** sia selezionata e quindi selezionare una delle opzioni seguenti in **Azione predefinita**:
    
      - **Allow**   consente al client di eseguire l'accesso se la versione client non corrisponde ad alcun filtro nell'elenco dei **criteri versione client** .
    
      - **Blocca**   impedisce l'accesso del client se la versione client non corrisponde ad alcun filtro nell'elenco dei **criteri versione client** .
    
      - **Blocca con URL**   impedisce al client di eseguire l'accesso se la versione client non corrisponde ad alcun filtro nell'elenco dei **criteri versione client** e include un messaggio di errore contenente un URL in cui è possibile scaricare un client più recente.
    
      - **Consenti con URL**   consente al client di eseguire l'accesso se la versione client non corrisponde ad alcun filtro nell'elenco dei **criteri versione client** e include un messaggio di errore contenente un URL in cui è possibile scaricare un client più recente.

6.  Se si seleziona **Blocca con URL**, digitare l'URL per il download del client da includere nel messaggio di errore nella casella **URL**.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-disable-client-version-control"></a>Per disabilitare il controllo delle versioni client

  - Per disabilitare il controllo delle versioni in modo da consentire l'accesso a tutti i client indipendentemente dalla versione del client, deselezionare la casella di controllo **Abilita controllo versione** e quindi fare clic su **Commit**.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Modifica dell'azione predefinita tramite i cmdlet di Windows PowerShell

L'azione predefinita da eseguire quando gli utenti tentano di accedere utilizzando client non esplicitamente supportati o limitati da un criterio di versione client possono essere gestiti utilizzando l'interfaccia della riga di comando di Windows PowerShell e il cmdlet **Set-CsClientVersionPolicy** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>Per configurare l'azione predefinita per bloccare l'accesso

  - Il comando seguente imposta l'azione predefinita per il blocco del sito Redmond. La registrazione è bloccata per i client per i quali non esiste una regola di configurazione della versione.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>Per configurare l'azione predefinita per consentire l'accesso

  - In questo esempio l'azione predefinita per il blocco del sito Redmond è Allow. La registrazione è consentita per i client per i quali non esiste una regola di configurazione della versione.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

