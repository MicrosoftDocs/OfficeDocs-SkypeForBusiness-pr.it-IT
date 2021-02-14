---
title: Gestire i provider federati SIP per l'organizzazione
ms.reviewer: ''
ms:assetid: c78d7e9b-c496-40c6-9249-06ced9cb87f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552455(v=OCS.15)
ms:contentKeyID: 48679566
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Informazioni su come configurare il supporto per gli utenti dei provider federati SIP.
ms.openlocfilehash: 8d4c6224a66454f8fb28bb4f991faf6ad672f596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823566"
---
# <a name="manage-sip-federated-providers-for-your-organization-in-skype-for-business-server"></a>Gestire i provider federati SIP per l'organizzazione in Skype for Business Server

Per configurare il supporto per gli utenti dei provider federati SIP, è necessario eseguire le operazioni seguenti:

  - Configurare uno o più criteri di accesso utente esterno per supportare la comunicazione con i contatti del provider federato SIP

  - Specificare quali provider ospitati si desidera supportare

  - Specificare quali provider di messaggistica istantanea pubblica si desidera supportare

## <a name="create-or-edit-public-sip-federated-providers-in-skype-for-business-server"></a>Creare o modificare provider federati SIP pubblici in Skype for Business Server

La connettività di messaggistica istantanea pubblica consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider pubblici.

Skype for Business Server include configurazioni di provider pubblici per la messaggistica istantanea. Ogni provider pubblico è configurato con il nome di dominio completo del server perimetrale del provider e il livello di verifica predefinito Consente agli utenti di comunicare solo con gli utenti del proprio elenco contatti che utilizzano **questo provider.**

Come impostazione predefinita, nessuno dei provider pubblici è abilitato. È consigliabile completare il contratto di licenza e il lavoro di provisioning prima di abilitare i provider pubblici. È possibile abilitare il provider prima di completare le operazioni di licenza e provisioning. Gli utenti non potranno comunicare con i contatti di tali provider fino al completamento del lavoro dei prerequisiti. Per informazioni dettagliate sulle licenze e sul provisioning dei provider pubblici, vedere [Configurare i criteri per controllare gli acces degli utenti pubblici.](../external-access-policies/configure-policies-to-control-public-user-access.md)

Utilizzare la procedura seguente per creare o modificare provider pubblici.


### <a name="to-create-or-edit-public-providers"></a>Per creare o modificare provider pubblici:

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Provider federati SIP**.

4.  Se è necessario creare un nuovo provider pubblico, fare clic su **Nuovo** e quindi su **Provider pubblico**.

5.  Se è necessario modificare una voce dell'elenco di provider pubblici, selezionare un provider pubblico, fare clic su **Modifica** e quindi su **Mostra dettagli**.

6.  Nella pagina **Modifica Provider federato SIP** è possibile digitare o modificare le impostazioni seguenti:
    
      - **Abilita comunicazioni con questo provider**   Se si seleziona questa impostazione, si abilita la messaggistica istantanea con gli utenti del provider specificato.
    
      - **Nome provider**   Si tratta di una proprietà obbligatoria. Digitare il nome del provider come verrà indicato nell'elenco di provider federati SIP.
    
      - **Servizio Access Edge (FQDN):**   Una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider che si sta configurando. Queste informazioni vengono fornite come elemento predefinito e devono essere modificate solo se il provider pubblico apporta una modifica all'FQDN del servizio Access Edge nel provider pubblico.
    
      - **Livello di verifica predefinito:**    L'impostazione predefinita, **Consenti agli utenti di comunicare solo con le persone incluse nell'elenco Contatti che usano questo provider** consente di comunicare solo con i contatti accettati e presenti nell'elenco contatti.
        
        Se si seleziona **Consenti agli utenti di comunicare con chiunque usi questo provider** rimuove la limitazione di dover ricevere e accettare l'invito di un contatto. Questa impostazione non impone limiti sugli utenti della rete del provider pubblico da cui si può essere contattati.

7.  Al termine della configurazione delle impostazioni, fare clic su **Commit** per salvare o su **Annulla** per annullare le modifiche.

## <a name="create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server"></a>Creare o modificare provider federati SIP ospitati in Skype for Business Server

La connettività di messaggistica istantanea del provider ospitato consente agli utenti dell'organizzazione di utilizzare la messaggistica istantanea per comunicare con gli utenti dei servizi di messaggistica istantanea forniti dai provider ospitati.

Ogni provider ospitato è configurato con il nome di dominio completo del server perimetrale del provider e il livello di verifica predefinito **Consenti agli utenti di comunicare solo con le persone incluse nell'elenco Contatti che usano questo provider**.

Utilizzare la procedura seguente per creare o modificare provider ospitati.

### <a name="to-create-or-edit-hosted-providers"></a>Per creare o modificare provider gestiti

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 

3.  Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Provider federati SIP**.

4.  Se è necessario creare un nuovo provider ospitato fare clic su **Nuovo** e quindi su **Provider ospitato**.

5.  Se è necessario modificare una voce nell'elenco di provider ospitati, selezionare un provider ospitato, fare clic su **Modifica** e quindi su **Mostra dettagli**.

6.  Nella pagina **Modifica provider federato SIP** è possibile immettere o modificare le seguenti impostazioni:
    
      - **Abilita comunicazioni con questo provider**   Questa impostazione abilita le comunicazioni con gli utenti del provider.
    
      - **Nome provider**   Si tratta di una proprietà obbligatoria. Digitare il nome del provider come verrà indicato nell'elenco di provider federati SIP.
    
      - **Servizio Access Edge (FQDN):**   Una proprietà obbligatoria, digitare il nome di dominio completo del servizio Access Edge del provider ospitato che si sta configurando. Queste informazioni devono essere fornite dal provider ospitato e devono essere modificate solo se il provider ospitato apporta una modifica all'FQDN del servizio Access Edge nel provider ospitato.
    
      - **Livello di verifica predefinito**   L'impostazione predefinita, ovvero **Consenti agli utenti di comunicare solo con le persone incluse nell'elenco Contatti che usano questo provider** limita le comunicazioni ai contatti che sono stati accettati e inclusi nell'elenco contatti.
        
        Se si seleziona **Consenti agli utenti di comunicare con chiunque usi questo provider**, viene rimossa la limitazione che prevede che sia stato ricevuto e accettato un invito di contatto. Questa impostazione non limita gli utenti dai quali è possibile essere contattati dalla rete del provider ospitato.

7.  Terminata la configurazione delle impostazioni, fare clic su **Commit** per salvare oppure su **Annulla** per annullare le modifiche.


## <a name="see-also"></a>Vedere anche


[Configurare i criteri per controllare gli acces degli utenti pubblici](../external-access-policies/configure-policies-to-control-public-user-access.md)

[Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

