---
title: 'Lync Server 2013: testare la distribuzione del pool'
description: 'Lync Server 2013: testare la distribuzione del pool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28101a252eda5048ded9f1eaf76c092c5cb7f986
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576042"
---
# <a name="test-the-pool-deployment-in-lync-server-2013"></a>Testare la distribuzione del pool in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-09-25_

Nella procedura seguente viene descritto come testare la distribuzione del pool Front end.

<div>

## <a name="to-test-the-pool-deployment"></a>Per testare la distribuzione di pool

1.  Utilizzare computer e utenti di Active Directory per aggiungere l'oggetto utente di Active Directory del ruolo di amministratore per la distribuzione di Lync Server 2013 (in cui è installato il pannello di controllo di Lync Server 2013) nel gruppo **CsAdministrator** .
    
    <div>
    

    > [!IMPORTANT]  
    > Se non si aggiungono gli utenti e i gruppi corretti al gruppo CSAdministrator, verrà visualizzato un messaggio di errore durante l'apertura del pannello di controllo di Lync Server, in cui viene indicato che "non autorizzato: accesso negato a causa di un errore di autorizzazione del controllo di accesso basato sui ruoli (RBAC)".

    
    </div>

2.  Se l'oggetto utente è connesso, disconnettersi e rieseguire l'accesso per registrare la nuova assegnazione al gruppo.
    
    <div>
    

    > [!NOTE]  
    > L'account utente non può essere l'amministratore locale di qualsiasi server che esegue Lync Server 2013.

    
    </div>

3.  Utilizzare l'account amministrativo per accedere al computer in cui è installato il pannello di controllo di Lync Server.

4.  Avviare il pannello di controllo di Lync Server e quindi specificare le credenziali, se richiesto. Nel pannello di controllo di Lync Server vengono visualizzate le informazioni sulla distribuzione.

5.  Sulla barra di spostamento sinistra fare clic su **topologia**e quindi verificare che lo stato del servizio visualizzi un computer con una freccia verde e che un segno di spunta verde per lo stato di replica sia accanto a ogni ruolo del server Lync Server distribuito e portato online.

6.  Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi su **Abilita utenti**.

7.  Nella pagina **Nuovo utente di Lync Server** fare clic su **Aggiungi**.

8.  Per definire i parametri di ricerca per gli oggetti che si desidera trovare, nella pagina **Seleziona da Active Directory** è possibile selezionare **Cerca** e quindi facoltativamente fare clic su **Aggiungi filtro**. È anche possibile selezionare **Ricerca LDAP** e immettere un'espressione LDAP per filtrare o limitare gli oggetti che verranno restituiti. Dopo aver deciso le opzioni di ricerca, fare clic su **Trova**.

9.  Nel riquadro dei risultati di ricerca selezionare tutti gli oggetti per questa sessione di ricerca e quindi fare clic su **OK**.

10. Nella pagina **Nuovo utente di Lync Server** l'oggetto o gli oggetti selezionati si trovano nella visualizzazione **Utenti**. Nell'elenco **Assegna utenti a un pool** selezionare il server in cui verranno ospitati gli oggetti.
    
    Di seguito sono riportate alcune opzioni di configurazione degli oggetti.
    
      - **Genera URI SIP utente**
    
      - **Telefonia**
    
      - **URI linea**
    
      - **Criteri conferenza**
    
      - **Criteri versione client**
    
      - **Criteri PIN**
    
      - **Criteri di accesso esterno**
    
      - **Criteri di archiviazione**
    
      - **Criteri percorso**
    
      - **Criteri client**
    
    Ai fini del test delle funzionalità di base, selezionare l'opzione preferita per l'impostazione **Genera URI SIP utente** (per le altre opzioni nella configurazione verranno utilizzate le impostazioni predefinite) e fare clic su **Abilita**.

11. Verrà visualizzata una pagina di riepilogo con un segno di spunta nella colonna **Abilitato** per indicare che gli oggetti sono pronti per l'uso. La colonna **Indirizzo SIP** visualizza l'indirizzo necessario per la configurazione dell'accesso degli utenti.

12. Connettere un utente a un computer appartenente al dominio e un altro utente a un altro computer nel dominio.

13. Installare Lync 2013 in ognuno dei due computer client e quindi verificare che entrambi gli utenti siano in grado di accedere a Lync Server 2013 e possano inviare messaggi istantanei.

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

