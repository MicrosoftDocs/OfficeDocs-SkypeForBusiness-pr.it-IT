---
title: "Lync Server 2013: configurare i criteri di conferenza per l'accesso esterno"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a74d49797565f643e36dfc59956ecc3ad73824e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Configurare i criteri di conferenza per l'accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-03-21_

I criteri di conferenza sono un'impostazione dell'account utente che specifica l'esperienza di conferenza per i partecipanti. È possibile creare criteri di conferenza con un ambito di sito o un ambito utente. Le impostazioni dei criteri di conferenza comprendono numerosi aspetti della pianificazione e della partecipazione alle conferenze. Numerose impostazioni dei criteri di conferenza supportano le conferenze telefoniche con accesso esterno per i partecipanti. Quando si configura una conferenza telefonica con accesso esterno, è necessario verificare che i campi siano impostati in modo appropriato per l'organizzazione e modificarli in base alle esigenze.

Verificare i campi seguenti nei criteri di conferenza:

  - **Consenti ai partecipanti di invitare utenti**   anonimi questa impostazione consente agli organizzatori di riunioni di invitare partecipanti anonimi, ovvero non autenticati, alle riunioni. Questa impostazione è facoltativa per le conferenze telefoniche con accesso esterno. Questa impostazione è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.

  - **Abilitare le conferenze telefoniche con accesso esterno**   PSTN Questa impostazione consente agli utenti di partecipare alla parte audio di una conferenza tramite la chiamata dalla rete PSTN. Questa impostazione è obbligatoria per le conferenze telefoniche con accesso esterno. Questa impostazione è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.

  - **Consenti ai partecipanti anonimi di**   effettuare la chiamata in uscita questa impostazione consente agli utenti anonimi che sono già stati aggiunti alla riunione di effettuare la chiamata a un numero di telefono per partecipare alla parte audio della conferenza. Questa impostazione è facoltativa per le conferenze telefoniche con accesso esterno. Questa impostazione non è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti.

  - **Consenti ai partecipanti non abilitati per VoIP aziendale di comporre**   questa impostazione consente ai partecipanti e agli organizzatori della riunione che non sono abilitati per VoIP aziendale di effettuare la chiamata a un numero di telefono per partecipare alla parte audio della conferenza. La chiamata in uscita è autorizzata in base ai criteri vocali assegnati all'organizzatore. Questa impostazione non è selezionata per impostazione predefinita nei criteri di conferenza globale predefiniti. Il valore predefinito dell'impostazione è Disabled.
    
    <div>
    

    > [!NOTE]  
    > Per abilitare questa funzionalità, un organizzatore di riunioni non abilitato per VoIP aziendale deve disporre di un criterio vocale appropriato assegnato per autorizzare qualsiasi chiamata in uscita da una conferenza organizzata dall'utente. È possibile assegnare un criterio vocale a un utente che non è abilitato per VoIP aziendale da Lync Server Management Shell. Se all'utente non è assegnato esplicitamente un criterio vocale, il criterio vocale del sito verrà utilizzato per autorizzare la richiesta di accesso esterno. Se non è presente alcun criterio vocale del sito, verrà utilizzato il criterio vocale globale.&nbsp;

    
    </div>

Nella procedura descritta in questa sezione viene illustrato come modificare i criteri di conferenza. Per informazioni dettagliate su come configurare tutte le impostazioni che definiscono l'esperienza dei partecipanti nei criteri di conferenza predefiniti, vedere [creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Per informazioni dettagliate sulla creazione di un criterio di conferenza per un utente o un gruppo di utenti specifico, vedere [Create or modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Per un elenco di tutte le impostazioni disponibili per i criteri di conferenza, vedere informazioni di [riferimento sulle impostazioni dei criteri di conferenza per Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>Per modificare i criteri di conferenza per l'accesso esterno

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Servizio di conferenza**.

4.  Nella scheda **criteri conferenza** fare doppio clic su un nome per i criteri di conferenza per aprire la finestra di dialogo **modifica criterio conferenza** .

5.  Verificare che i campi per le conferenze telefoniche con accesso esterno siano adatti all'organizzazione e modificare le impostazioni, se necessario.

6.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

