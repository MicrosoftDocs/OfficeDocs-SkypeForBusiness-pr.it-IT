---
title: 'Lync Server 2013: creare o modificare provider federati SIP ospitati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7704074db1b210ca341b05df9fbd02afabbc70a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507493"
---
# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>Creare o modificare provider federati SIP ospitati Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

La connettività di messaggistica istantanea (IM) del provider hosted consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti da provider ospitati, tra cui Microsoft 365 e Lync Online.

Ogni provider ospitato è configurato con il nome di dominio completo del server perimetrale del provider e il livello di verifica predefinito **Consenti agli utenti di comunicare solo con le persone incluse nell'elenco Contatti che usano questo provider**.

Per creare o modificare provider gestiti, eseguire la procedura seguente:

<div>

## <a name="to-create-or-edit-hosted-providers"></a>Per creare o modificare provider gestiti

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Provider federati SIP**.

4.  Se è necessario creare un nuovo provider ospitato fare clic su **Nuovo** e quindi su **Provider ospitato**.

5.  Se è necessario modificare una voce nell'elenco di provider ospitati, selezionare un provider ospitato, fare clic su **Modifica** e quindi su **Mostra dettagli**.

6.  Nella pagina **Modifica provider federato SIP** è possibile immettere o modificare le seguenti impostazioni:
    
      - **Abilitare le comunicazioni con questo provider**     Selezionando questa impostazione, viene abilitata la comunicazione con gli utenti del provider.
    
      - **Nome provider:**     Una proprietà obbligatoria, digitare il nome del provider come verrà riflesso nell'elenco dei provider federati SIP.
    
      - **Servizio Access Edge (FQDN):**     Una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider ospitato che si sta configurando. Queste informazioni devono essere fornite dal provider ospitato e devono essere modificate solo se il provider ospitato apporta una modifica al nome di dominio completo del servizio Access Edge nel provider ospitato.
    
      - **Livello di verifica predefinito:**     L'impostazione predefinita **consente agli utenti di comunicare con le persone presenti nell'elenco contatti che usano questo provider** limiterà la comunicazione ai contatti accettati e che si trovano nell'elenco dei contatti.
        
        Se si seleziona **Consenti agli utenti di comunicare con chiunque usi questo provider**, viene rimossa la limitazione che prevede che sia stato ricevuto e accettato un invito di contatto. Questa impostazione non limita gli utenti dai quali è possibile essere contattati dalla rete del provider ospitato.

7.  Terminata la configurazione delle impostazioni, fare clic su **Commit** per salvare oppure su **Annulla** per annullare le modifiche.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione di criteri per il controllo dell'accesso degli utenti pubblici in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

