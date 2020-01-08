---
title: 'Lync Server 2013: Testare la distribuzione di pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a1dc68b8dbe6285cdf4b7e9c21c873caaf730d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Testare la distribuzione di pool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-09-25_

La procedura seguente descrive come testare la distribuzione del pool Front-end.

<div>

## <a name="to-test-the-pool-deployment"></a>Per testare la distribuzione del pool

1.  Usare i computer e gli utenti di Active Directory per aggiungere l'oggetto utente di Active Directory del ruolo di amministratore per la distribuzione di Lync Server 2013 (in cui è installato il pannello di controllo di Lync Server 2013) al gruppo **CsAdministrator** .
    
    <div>
    

    > [!IMPORTANT]  
    > Se non si aggiungono gli utenti e i gruppi appropriati al gruppo CsAdministors, viene visualizzato un messaggio di errore quando si apre il pannello di controllo di Lync Server, in cui viene indicato che non è stato autorizzato l'accesso a causa di un errore di autorizzazione del controllo di accesso basato sui ruoli (RBAC).

    
    </div>

2.  Se l'oggetto utente è attualmente connesso, disconnettersi e quindi accedere di nuovo per registrare la nuova assegnazione del gruppo.
    
    <div>
    

    > [!NOTE]  
    > L'account utente non può essere l'amministratore locale di qualsiasi server che esegua Lync Server 2013.

    
    </div>

3.  Usare l'account amministrativo per accedere al computer in cui è installato il pannello di controllo di Lync Server.

4.  Avviare il pannello di controllo di Lync Server e quindi specificare le credenziali, se richiesto. Il pannello di controllo di Lync Server Visualizza le informazioni sulla distribuzione.

5.  Nella barra di spostamento sinistra fare clic su **topologia**e quindi verificare che lo stato del servizio visualizzi un computer con una freccia verde e che un segno di spunta verde per lo stato di replica sia accanto a ogni ruolo di Lync Server Server distribuito e portato online.

6.  Sulla barra di spostamento sinistra fare clic su **utenti**e quindi su **Abilita utenti**.

7.  Nella pagina **nuovo utente di Lync Server** fare clic su **Aggiungi**.

8.  Per definire i parametri di ricerca per gli oggetti che si desidera trovare, nella pagina **Seleziona da Active Directory** è possibile selezionare **ricerca**e quindi fare clic su **Aggiungi filtro**. È anche possibile selezionare **ricerca LDAP** e immettere un'espressione LDAP per filtrare o limitare gli oggetti che verranno restituiti. Dopo aver deciso le opzioni di ricerca, vedere Clink **Find**.

9.  Nel riquadro Risultati ricerca selezionare tutti gli oggetti per la sessione di ricerca e quindi fare clic su **OK**.

10. Nella **nuova pagina utente di Lync Server** l'oggetto o gli oggetti selezionati si trovano nella visualizzazione **utenti** . Nell'elenco **Assegna utenti a un pool** selezionare il server in cui devono essere assegnati gli oggetti.
    
    Di seguito sono riportate alcune opzioni per la configurazione degli oggetti.
    
      - **Generare l'URI SIP dell'utente**
    
      - **Telefonia**
    
      - **URI di linea**
    
      - **Criteri di conferenza**
    
      - **Criteri di versione client**
    
      - **Criteri PIN**
    
      - **Criteri di accesso esterno**
    
      - **Criteri di archiviazione**
    
      - **Criteri posizione**
    
      - **Criteri client**
    
    Per testare le funzionalità di base, selezionare l'opzione preferita per l'impostazione **URI SIP dell'utente** (le altre opzioni della configurazione utilizzeranno le impostazioni predefinite) e quindi fare clic su **Abilita**.

11. Viene visualizzata una pagina di riepilogo che mostra un segno di spunta nella colonna **Enabled** per indicare che gli oggetti sono ora pronti per l'uso. Nella colonna **indirizzo SIP** viene visualizzato l'indirizzo necessario per la configurazione di accesso dell'utente.

12. È necessario registrare un utente in un computer collegato al dominio e un altro utente in un altro computer del dominio.

13. Installare Lync 2013 in ognuno dei due computer client e verificare che entrambi gli utenti possano accedere a Lync Server 2013 e inviare messaggi istantanei.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione di client e dispositivi in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

