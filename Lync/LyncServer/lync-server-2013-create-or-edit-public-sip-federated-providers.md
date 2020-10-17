---
title: 'Lync Server 2013: creare o modificare provider federati SIP pubblici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58b0ffdc009d48ef82d1bdf3ba8662cd4072ea1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514853"
---
# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Creare o modificare provider federati SIP pubblici in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblici, inclusi Windows Live Messenger, Yahoo \! e AOL.

Lync Server 2013 dispone di configurazioni di provider pubblici per America Online, Windows Live e Yahoo\! messaggistica immediata. Ogni provider pubblico è configurato con il nome di dominio completo del server perimetrale del provider e il livello di verifica predefinito **consente agli utenti di comunicare solo con le persone presenti nell'elenco dei contatti che utilizzano questo provider**.

Come impostazione predefinita, nessuno dei provider pubblici è abilitato. Prima di abilitare i provider pubblici, è necessario completare il contratto di licenza e il provisioning. È possibile abilitare il provider prima di completare il lavoro di gestione delle licenze e del provisioning. Gli utenti non saranno in grado di comunicare con i contatti su tali provider fino al completamento del lavoro prerequisito. Per informazioni dettagliate sulle licenze e il provisioning dei provider pubblici, vedere [Configure policies to Control public User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Per creare o modificare provider pubblici, eseguire la procedura seguente:

<div>

## <a name="to-create-or-edit-public-providers"></a>Per creare o modificare provider pubblici:

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Provider federati SIP**.

4.  Se è necessario creare un nuovo provider pubblico, fare clic su **Nuovo** e quindi su **Provider pubblico**.

5.  Se è necessario modificare una voce dell'elenco di provider pubblici, selezionare un provider pubblico, fare clic su **Modifica** e quindi su **Mostra dettagli**.

6.  Nella pagina **Modifica Provider federato SIP** è possibile digitare o modificare le impostazioni seguenti:
    
      - **Abilitare le comunicazioni con questo provider**     Selezionando questa impostazione, viene abilitata la messaggistica istantanea con gli utenti del provider.
    
      - **Nome provider:**     Una proprietà obbligatoria, digitare il nome del provider come verrà riflesso nell'elenco dei provider federati SIP.
    
      - **Servizio Access Edge (FQDN):**     Una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider che si sta configurando. Queste informazioni vengono fornite come elementi predefiniti e devono essere modificate solo se il provider pubblico apporta una modifica al nome di dominio completo del servizio Access Edge nel provider pubblico.
    
      - **Livello di verifica predefinito:**     L'impostazione predefinita **consente agli utenti di comunicare con le persone presenti nell'elenco contatti che usano questo provider** limiterà la comunicazione ai contatti accettati e che si trovano nell'elenco dei contatti.
        
        Se si seleziona **Consenti agli utenti di comunicare con chiunque usi questo provider** rimuove la limitazione di dover ricevere e accettare l'invito di un contatto. Questa impostazione non impone limiti sugli utenti della rete del provider pubblico da cui si può essere contattati.

7.  Al termine della configurazione delle impostazioni, fare clic su **Commit** per salvare o su **Annulla** per annullare le modifiche.

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

