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
ms.openlocfilehash: 806bdf8ac43c8126e0537ccb121cbc521066aab6cd42c7136d0d8b951d5b9d19
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319459"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurare l'archivio contatti personali nei computer client Lync 2010
  
Se si sta integrando Skype for Business Server 2015 e Exchange Server 2016 o Exchange Server 2013, è necessario configurare l'archivio contatti personale utilizzato dai client. In particolare, è consigliabile configurare Skype for Business per l'utilizzo di Exchange come archivio contatti personale e, allo stesso tempo, assicurarsi che gli utenti non siano in grado di ignorare tale decisione. A tale scopo, è possibile creare e configurare un valore del Registro di sistema in ogni computer client.
  
> [!NOTE]
> La procedura seguente è necessaria solo per i client che utilizzano il client Lync 2010 o versioni precedenti. Il client Lync 2013 e tutti Skype for Business non avranno la possibilità di ignorare le impostazioni dell'archivio contatti.
  
Per configurare questo valore in un singolo computer, eseguire la procedura seguente:
  
1. Nel computer client fare clic sul pulsante **Start** e quindi scegliere **Esegui.**
2. Nella finestra di dialogo **Esegui** digitare regedit e quindi premere INVIO.
3. Nell'Editor del Registro di **sistema espandere HKEY_LOCAL_MACHINE**, **software**, **Criteri**, **Microsoft** e quindi espandere **Communicator**.
4. Fare clic con **il Communicator,** scegliere **Nuovo** e quindi **valore DWORD (32 bit).**
5. Dopo aver creato il nuovo valore, digitare PersonalContactStoreOverride e quindi premere INVIO per rinominare il valore.
6. Verificare che il valore di PersonalContactStoreOverride sia impostato su 0 e quindi chiudere l'editor del Registro di sistema.

Se si desidera eseguire le stesse modifiche in più computer è possibile creare un oggetto Criteri di gruppo personalizzato. Per informazioni dettagliate su questa operazione in Windows 10, vedere [l'articolo Creare un oggetto Criteri di](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) gruppo.
