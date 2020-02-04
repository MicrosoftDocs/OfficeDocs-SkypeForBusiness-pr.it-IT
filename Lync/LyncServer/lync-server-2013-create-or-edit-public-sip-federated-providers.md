---
title: 'Lync Server 2013: Creare o modificare provider federati SIP pubblici'
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
ms.openlocfilehash: 33303217e6e1a1fefb502f1e9b364a46adc85e02
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Creare o modificare provider federati SIP pubblici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di usare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider di servizi di messaggistica istantanea pubblici,\!tra cui Windows Live Messenger, Yahoo e AOL.

Lync Server 2013 include configurazioni di provider pubbliche per America Online, Windows Live e Yahoo\! messaggistica istantanea. Ogni provider pubblico è configurato con il nome di dominio completo di Edge Server del provider e il livello di verifica predefinito **consente agli utenti di comunicare solo con persone presenti nell'elenco contatti che usano questo provider**.

Come impostazione predefinita, nessuno dei provider pubblici è abilitato. Prima di abilitare i provider pubblici, è consigliabile completare il contratto di licenza e il provisioning. È possibile abilitare il provider prima di completare il lavoro di licenza e provisioning. Gli utenti non saranno in grado di comunicare con i contatti di tali provider finché non viene completato il lavoro pre-requisito. Per informazioni dettagliate sulle licenze e sul provisioning dei provider pubblici, vedere [configurare i criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Usare la procedura seguente per creare o modificare provider pubblici:

<div>

## <a name="to-create-or-edit-public-providers"></a>Per creare o modificare provider pubblici

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi fare clic su **provider federati SIP**.

4.  Se è necessario creare un nuovo provider pubblico, fare clic su **nuovo** e quindi su **provider pubblico**.

5.  Se è necessario modificare una voce dall'elenco di provider pubblici, selezionare un provider pubblico, fare clic su **modifica**e quindi su **Mostra dettagli**.

6.  Nella pagina **Modifica provider FEDERATO SIP** è possibile digitare o modificare le impostazioni seguenti:
    
      - **Abilitare le comunicazioni con questo provider**   la selezione di questa impostazione consente agli utenti di questo provider di usare la messaggistica istantanea.
    
      - **Nome provider:**   una proprietà obbligatoria, digitare il nome del provider che verrà riflesso nell'elenco dei provider federati SIP.
    
      - **Access Edge service (FQDN):**   una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider che si sta configurando. Queste informazioni vengono fornite come elemento predefinito e devono essere modificate solo se il provider pubblico apporta una modifica al nome di dominio completo del servizio Access Edge presso il provider pubblico.
    
      - **Livello di verifica predefinito:**   l'impostazione predefinita **consente agli utenti di comunicare con persone nell'elenco contatti che usano questo provider** limiterà la comunicazione ai contatti accettati e inclusi nell'elenco contatti.
        
        Selezionando **Consenti agli utenti di comunicare con tutti i membri che usano questo provider** , viene eliminata la restrizione che deve essere stata ricevuta e accettata da un contatto. Questa impostazione non limita chi può contattarti dalla rete del provider pubblico.

7.  Dopo aver configurato le impostazioni, fare clic su **conferma** per salvare o su **Annulla per annullare** le modifiche.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare criteri per controllare l'accesso degli utenti pubblici in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

