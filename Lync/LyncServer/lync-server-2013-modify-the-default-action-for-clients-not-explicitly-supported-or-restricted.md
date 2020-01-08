---
title: Modificare l'azione predefinita per i client non esplicitamente supportati o limitati
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b364253a87f1cbff1ef60322c65780b6497880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Modificare l'azione predefinita per i client non esplicitamente supportati o limitati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Oltre a specificare la versione dei client che si vuole supportare nell'ambiente Lync Server 2013, è anche possibile specificare un'azione predefinita per i client che non hanno già un criterio di versione definito. Ciò consente di limitare le versioni client usate nell'ambiente Lync Server, che consentono di controllare i costi associati al supporto di più versioni client.

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>Per modificare l'azione predefinita per i client non esplicitamente supportati o limitati

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi su **Configurazione versione client**.

4.  Nella pagina **Configurazione versione client** fare doppio clic sulla configurazione **globale** nell'elenco.

5.  Nella finestra di dialogo **modifica configurazione versione client** verificare che sia selezionata la casella di **controllo Enable Version Control** e quindi, in **azione predefinita**, selezionare una delle opzioni seguenti:
    
      - **Consenti**   consente al client di accedere se la versione client non corrisponde a un filtro nell'elenco dei **criteri di versione client** .
    
      - **Il blocco**   impedisce che il client acceda se la versione client non corrisponde a un filtro nell'elenco dei **criteri di versione client** .
    
      - **Il blocco con URL**   impedisce che il client acceda se la versione client non corrisponde a un filtro nell'elenco dei **criteri di versione client** e include un messaggio di errore contenente un URL in cui è possibile scaricare un nuovo client.
    
      - **Consenti con URL**   consente al client di accedere se la versione client non corrisponde a un filtro nell'elenco dei **criteri di versione client** e di includere un messaggio di errore contenente un URL in cui è possibile scaricare un nuovo client.

6.  Se si è selezionato **blocca con URL**, digitare l'URL di download del client da includere nel messaggio di errore nella casella **URL** .

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-disable-client-version-control"></a>Per disabilitare il controllo della versione client

  - Per disabilitare il controllo della versione per consentire l'accesso a tutti i client indipendentemente dalla versione del client, deselezionare la casella di controllo **Enable Version Control** e quindi fare clic su **commit**.

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Modifica dell'azione predefinita con i cmdlet di Windows PowerShell

L'azione predefinita da eseguire quando gli utenti provano a eseguire l'accesso usando client non esplicitamente supportati o limitati da criteri di versione client possono essere gestiti usando l'interfaccia della riga di comando di Windows PowerShell e il cmdlet **Set-CsClientVersionPolicy** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>Per configurare l'azione predefinita per bloccare l'accesso

  - Il comando seguente imposta l'azione predefinita per il blocco di sito Redmond. In questo modo si bloccherà la registrazione per qualsiasi client per cui non esiste alcuna regola di configurazione della versione client.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>Per configurare l'azione predefinita per consentire l'accesso

  - In questo esempio l'azione predefinita per il sito Redmond è impostata su Consenti. Ciò consentirà la registrazione per qualsiasi client per cui non esiste alcuna regola di configurazione della versione client.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) .

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

