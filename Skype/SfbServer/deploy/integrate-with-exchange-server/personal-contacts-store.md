---
title: Configurare l'archivio contatti personali nei computer client Lync 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: "Riepilogo: configurare l'archivio contatti personale utilizzato dai client legacy."
ms.openlocfilehash: 66ef1c3726ea020669894769b48b2313e1da2e0e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833936"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurare l'archivio contatti personali nei computer client Lync 2010
  
Se stai integrando Skype for Business Server 2015 e Exchange Server 2016 o Exchange Server 2013, devi configurare l'archivio contatti personale usato dai client. In particolare, è necessario configurare Skype for Business per l'utilizzo di Exchange come archivio contatti personale e, allo stesso tempo, assicurarsi che gli utenti non siano in grado di ignorare tale decisione. A tale scopo, è possibile creare e configurare un valore del Registro di sistema in ogni computer client.
  
> [!NOTE]
> La procedura seguente è necessaria solo per i client che utilizzano il client Lync 2010 o versioni precedenti. Il client Lync 2013 e tutti i client Skype for Business non avranno la possibilità di ignorare le impostazioni dell'archivio contatti.
  
Per configurare questo valore in un singolo computer, eseguire la procedura seguente:
  
1. Nel computer client fare clic sul pulsante **Start** e quindi scegliere **Esegui.**
2. Nella finestra di dialogo **Esegui** digitare regedit e quindi premere INVIO.
3. Nell'Editor del Registro di sistema espandere **HKEY_LOCAL_MACHINE**, **software**, **criteri**, **Microsoft** e quindi **espandere** Communicator .
4. Fare clic con **il Communicator,** scegliere **Nuovo** e quindi **valore DWORD (32 bit).**
5. Dopo aver creato il nuovo valore, digitare PersonalContactStoreOverride e quindi premere INVIO per rinominare il valore.
6. Verificare che il valore di PersonalContactStoreOverride sia impostato su 0 e quindi chiudere l'editor del Registro di sistema.

Se si desidera eseguire le stesse modifiche in più computer è possibile creare un oggetto Criteri di gruppo personalizzato. Per informazioni dettagliate su questa operazione in Windows 10, vedi l'articolo [Creare un oggetto Criteri di](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) gruppo.
  
