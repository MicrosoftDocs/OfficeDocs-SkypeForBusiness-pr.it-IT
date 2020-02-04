---
title: "Lync Server 2013: configurazione della CA aziendale per l'autenticazione tramite smart card"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44df62031e679c641b4c7dbe6b5c205e1ae899e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Configurazione della CA aziendale per l'autenticazione tramite smart card in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-03_

La sezione seguente descrive come configurare un'autorità di certificazione (CA) aziendale per supportare l'autenticazione tramite smart card. Per informazioni su come installare una CA radice aziendale, vedere installare un'autorità di [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)certificazione radice aziendale.

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurazione di un'autorità di certificazione radice aziendale per supportare l'autenticazione tramite smart card

La procedura seguente descrive come configurare una CA radice aziendale per supportare l'autenticazione tramite smart card:

1.  Accedere al computer della CA aziendale usando un account di amministratore di dominio.

2.  Avviare System Manager e verificare che sia installato il ruolo di registrazione Web Authority Certificate.

3.  Nel menu **strumenti di amministrazione** aprire la console di gestione **autorità di certificazione** .

4.  Nel riquadro di spostamento espandere **autorità di certificazione**.

5.  Fare clic con il pulsante destro del mouse sui **modelli di certificato**, scegliere **nuovo**e quindi **modello certificato da emettere**.

6.  Selezionare **agente di registrazione**, **utente smartcard**e accesso tramite **smartcard**.

7.  Fare clic su **OK**.

8.  Fare clic con il pulsante destro sul **modello di certificato**.

9.  Selezionare **Gestisci**.

10. Aprire le proprietà del modello utente smartcard.

11. Fare clic sulla scheda **sicurezza** .

12. Modificare le autorizzazioni nel modo seguente:
    
      - Aggiungere singoli account di annunci utente con autorizzazioni di lettura/registrazione (Consenti) oppure
    
      - Aggiungere un gruppo di sicurezza contenente gli utenti di smart card con autorizzazioni di lettura/registrazione (Consenti) oppure
    
      - Aggiungere il gruppo Domain Users con le autorizzazioni di lettura/registrazione (Consenti)

</div>

</div>

<span> </span>

</div>

</div>

</div>

