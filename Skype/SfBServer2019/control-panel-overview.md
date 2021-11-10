---
title: Pannello di controllo - Panoramica
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/13/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: In questo articolo viene fornita una panoramica del nuovo Pannello di controllo.
ms.openlocfilehash: 355a8b93e428b860a775ad01cf31df726c644654
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887304"
---
# <a name="control-panel"></a>Pannello di controllo

Il Pannello di controllo corrente è una nuova versione del Pannello di controllo legacy, con cui esiste in tandem. Il nuovo Pannello di controllo è stato creato dall'aggiornamento cumulativo di luglio 2019. Consente di gestire la configurazione di server, utenti, client e dispositivi nell'ambiente di un'organizzazione.

Il Pannello di controllo legacy potrebbe non funzionare poiché la tecnologia Silverlight ha raggiunto la fase di "fine del supporto" il 12 ottobre 2021. Per ulteriori informazioni, vedere [Silverlight End of Support.](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788)

> [!NOTE]
> Per informazioni sul Pannello di controllo legacy, vedi [Pannello di controllo](../SfbServer/management-tools/install-and-open-administrative-tools.md)e passa alla sezione Skype for Business Server Pannello di **controllo.**

## <a name="access-control-panel"></a>Pannello di controllo di accesso

Per avviare il nuovo Pannello di controllo nel browser, immettere https:// &lt; pool-FQDN &gt; /macp o un URL semplice configurato.

Il nuovo Pannello di controllo include voci di menu di uso comune che riguardano la maggior parte delle esigenze dell'organizzazione. Alcune voci di menu del Pannello di controllo legacy non sono disponibili nel nuovo Pannello di controllo. Tuttavia, esiste un'opzione che consente all'utente di utilizzare le funzionalità di tali voci di menu tramite i cmdlet di PowerShell. Per ulteriori informazioni, vedere la tabella seguente.

> [!NOTE]
> La documentazione per altre voci di menu verrà resa disponibile successivamente in modo graduale.

## <a name="client"></a>Client

|Sottomenu  |Origine delle informazioni per il cmdlet  |
|---------|---------|
|Criteri delle versioni client         |    [Criteri delle versioni client](use-powershell-client-menu.md#client-version-policy)     |
|Configurazione versione client      |  [Configurazione delle versioni client](use-powershell-client-menu.md#client-version-configuration)       |
|Aggiornamento dispositivi    | [Aggiornamento dei dispositivi](use-powershell-client-menu.md#device-update)        |
|Dispositivo di test     | [Dispositivo di test](use-powershell-client-menu.md#test-device)        |
|Configurazione dei log del dispositivo         |    [Configurazione dei log del dispositivo](use-powershell-client-menu.md#device-log-configuration)     |
|Configurazione dispositivo         |    [Configurazione dispositivo](use-powershell-client-menu.md#device-configuration)     |
|Criteri per dispositivi mobili         |    [Criteri per dispositivi mobili](use-powershell-client-menu.md#mobility-policy)     |
|Configurazione notifica Push         |    [Configurazione notifica Push](use-powershell-client-menu.md#push-notification-configuration)     |

## <a name="security"></a>Sicurezza

|Sottomenu  |Origine delle informazioni per il cmdlet  |
|---------|---------|
|Registrar         |    [Registrar](use-powershell-security-menu.md#registrar)     |
|Web Service      |  [Web Service](use-powershell-security-menu.md#web-service)       |
|Criteri PIN    | [Criteri PIN](use-powershell-security-menu.md#pin-policy)        |

## <a name="im-and-presence"></a>Messaggistica istantanea e presenza

|Sottomenu  |Origine delle informazioni per il cmdlet  |
|---------|---------|
|Filtro file         |    [Filtro file](use-powershell-im-and-presence-menu.md#file-filter)     |
|Filtro URL      |  [Filtro URL](use-powershell-im-and-presence-menu.md#url-filter)       |
