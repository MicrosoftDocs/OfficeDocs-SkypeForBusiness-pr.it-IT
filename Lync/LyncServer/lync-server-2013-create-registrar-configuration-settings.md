---
title: 'Lync Server 2013: creare impostazioni di configurazione del registrar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81aec9ee6923dc125769ad16a26390b23155852c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Creare impostazioni di configurazione del registrar in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-17_

È possibile usare il registrar per configurare i metodi di autenticazione del server proxy. Il protocollo di autenticazione specificato determina il tipo di problemi che i server del pool rilasciano ai client. I protocolli disponibili sono:

  - **Kerberos**   questo è lo schema di autenticazione basato su password più forte disponibile per i client, ma in genere è disponibile solo per i client aziendali, perché richiede la connessione del client a un centro distribuzione chiave (controller di dominio Kerberos). Questa impostazione è appropriata se il server autentica solo i client aziendali.

  - **NTLM**   questa è l'autenticazione basata su password disponibile per i client che usano uno schema di hash per la risposta alla richiesta di verifica sulla password. Questa è l'unica forma di autenticazione disponibile per i client senza connettività a un centro distribuzione chiave (controller di dominio Kerberos), ad esempio utenti remoti. Se un server esegue l'autenticazione solo per gli utenti remoti, è necessario scegliere NTLM.

  - **Autenticazione del certificato**   questo è il nuovo metodo di autenticazione quando il server deve ottenere certificati da client di Lync Phone Edition, telefoni area comune, Lync 2013 e l'app Lync di Windows Store. Nei client di Lync Phone Edition, dopo che un utente ha eseguito l'accesso e viene autenticato fornendo un PIN (Personal Identification Number), Lync Server 2013 fornisce quindi l'URI SIP al telefono e prevede un certificato firmato da Lync Server o un certificato utente che identifica Joe (es: SN=joe@contoso.com) sul telefono. Questo certificato viene usato per l'autenticazione con il registrar e i servizi Web.

<div>


> [!NOTE]  
> È consigliabile abilitare sia Kerberos che NTLM quando un server supporta l'autenticazione sia per i client remoti che per quelli aziendali. Il server perimetrale e i server interni comunicano per garantire che solo l'autenticazione NTLM venga offerta ai client remoti. Se in questi server è abilitato solo Kerberos, non è possibile eseguire l'autenticazione degli utenti remoti. Se gli utenti aziendali eseguono l'autenticazione anche sul server, viene usato Kerberos.<BR>Se si utilizzeranno i client delle app Lync di Windows Store, è necessario abilitare l'autenticazione dei certificati.



</div>

Seguire questa procedura per creare un nuovo registrar.

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>Per creare nuove impostazioni di configurazione del registrar

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **registrar**.

4.  Nella pagina **registrar** fare clic su **nuovo**

5.  In **Seleziona un servizio**fare clic sul servizio a cui deve essere applicato il registrar e quindi fare clic su **OK**.

6.  In **nuova impostazione registrar**selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:
    
      - **Abilitare l'autenticazione Kerberos per consentire** ai server del pool di emettere problemi con l'autenticazione Kerberos.
    
      - **Abilitare l'autenticazione NTLM per consentire** ai server del pool di emettere problemi con NTLM.
    
      - **Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.

7.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

