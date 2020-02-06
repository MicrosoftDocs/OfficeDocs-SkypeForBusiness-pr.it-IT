---
title: Gestire i provider federati SIP per l'organizzazione
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Informazioni su come configurare il supporto per gli utenti di provider federati SIP.
ms.openlocfilehash: 42845bfd39c65e60765ee8d3fd2f1e3a58a08aae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818367"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Gestire i provider federati SIP per l'organizzazione in Skype for Business Server

Per configurare il supporto per gli utenti di provider federati SIP, è necessario eseguire le operazioni seguenti:

  - Configurare uno o più criteri di accesso degli utenti esterni per supportare la comunicazione con i contatti del provider federativo SIP

  - Specificare i provider ospitati che si desidera supportare

  - Specificare i provider di messaggistica istantanea pubblici che si desidera supportare

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Creare o modificare provider federati SIP pubblici in Skype for Business Server

La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di usare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider pubblici.

Skype for Business Server include configurazioni di provider pubbliche per la messaggistica istantanea. Ogni provider pubblico è configurato con il nome di dominio completo di Edge Server del provider e il livello di verifica predefinito **consente agli utenti di comunicare solo con persone presenti nell'elenco contatti che usano questo provider**.

Come impostazione predefinita, nessuno dei provider pubblici è abilitato. Prima di abilitare i provider pubblici, è consigliabile completare il contratto di licenza e il provisioning. È possibile abilitare il provider prima di completare il lavoro di licenza e provisioning. Gli utenti non saranno in grado di comunicare con i contatti di tali provider finché non viene completato il lavoro pre-requisito. Per informazioni dettagliate sulle licenze e sul provisioning dei provider pubblici, vedere [configurare i criteri per controllare l'accesso degli utenti pubblici](../external-access-policies/configure-policies-to-control-public-user-access.md).

Usare la procedura seguente per creare o modificare provider pubblici.


### <a name="to-create-or-edit-public-providers"></a>Per creare o modificare provider pubblici

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

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

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Creare o modificare provider federati SIP ospitati in Skype for Business Server

La connettività di messaggistica istantanea del provider ospitata consente agli utenti dell'organizzazione di usare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider ospitati.

Ogni provider ospitato è configurato con il nome di dominio completo del server perimetrale del provider e il livello di verifica predefinito **consente agli utenti di comunicare solo con persone presenti nell'elenco contatti che usano questo provider**.

Usare la procedura seguente per creare o modificare i provider ospitati.

### <a name="to-create-or-edit-hosted-providers"></a>Per creare o modificare i provider ospitati

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 

3.  Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**, quindi fare clic su **provider federati SIP**.

4.  Se è necessario creare un nuovo provider ospitato, fare clic su **nuovo** e quindi su **provider ospitati**.

5.  Se è necessario modificare una voce dall'elenco di provider ospitati, selezionare un provider ospitata, fare clic su **modifica**e quindi su **Mostra dettagli**.

6.  Nella pagina **Modifica provider FEDERATO SIP** è possibile digitare o modificare le impostazioni seguenti:
    
      - **Abilitare le comunicazioni con questo provider**   Selezionare questa impostazione consente le comunicazioni con gli utenti del provider.
    
      - **Nome provider:**   una proprietà obbligatoria, digitare il nome del provider che verrà riflesso nell'elenco dei provider federati SIP.
    
      - **Access Edge service (FQDN):**   una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider ospitato che si sta configurando. Queste informazioni devono essere fornite dal provider ospitato e devono essere modificate solo se il provider ospitato apporta una modifica all'FQDN del servizio Access Edge presso il provider ospitata.
    
      - **Livello di verifica predefinito:**   l'impostazione predefinita **consente agli utenti di comunicare con persone nell'elenco contatti che usano questo provider** limiterà la comunicazione ai contatti accettati e inclusi nell'elenco contatti.
        
        Selezionando **Consenti agli utenti di comunicare con tutti i membri che usano questo provider** , viene eliminata la restrizione che deve essere stata ricevuta e accettata da un contatto. Questa impostazione non limita chi può contattarti dalla rete del provider ospitata.

7.  Dopo aver configurato le impostazioni, fare clic su **conferma** per salvare o su **Annulla per annullare** le modifiche.


## <a name="see-also"></a>Vedere anche


[Configurare i criteri per controllare l'accesso degli utenti pubblici](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

