---
title: Configurare l'archivio dei contatti personali nei computer client di Lync 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: "Riepilogo: configurare l'archivio contatti personale usato dai client legacy."
ms.openlocfilehash: a80af6ca575b53e5a2b8f77a109fd6929f0db704
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797027"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Configurare l'archivio dei contatti personali nei computer client di Lync 2010
  
Se si integrano Skype for Business Server 2015 ed Exchange Server 2016 o Exchange Server 2013, è necessario configurare l'archivio contatti personale usato dai client. In particolare, devi configurare Skype for business in modo da usare Exchange come archivio contatti personale e, allo stesso tempo, assicurarti che gli utenti non siano in grado di ignorare tale decisione. Questa operazione può essere eseguita creando e configurando un valore del registro di sistema in ogni computer client.
  
> [!NOTE]
> La procedura seguente è necessaria solo per i client che usano il client Lync 2010 o versioni precedenti. Il client Lync 2013 e tutti i client Skype for business non avranno la possibilità di eseguire l'override delle impostazioni dell'archivio contatti.
  
Per configurare questo valore in un singolo computer, eseguire la procedura seguente:
  
1. Nel computer client fare clic su **Start** e quindi su **Esegui**.
2. Nella finestra di dialogo **Esegui** Digitare regedit e quindi premere INVIO.
3. In Editor del registro di sistema Espandi **HKEY_LOCAL_MACHINE**, Espandi **software**, Espandi **criteri**, Espandi **Microsoft**e quindi Espandi **Communicator**.
4. Fare clic con il pulsante destro del mouse su **Communicator**, scegliere **nuovo**e quindi fare clic su **valore DWORD (32 bit)**.
5. Dopo la creazione del nuovo valore, digitare PersonalContactStoreOverride e quindi premere INVIO per rinominare il valore.
6. Verificare che il valore di PersonalContactStoreOverride sia impostato su 0 e quindi chiudere l'editor del registro di sistema.

Se è necessario apportare questa stessa modifica su più computer, è possibile creare un oggetto Criteri di gruppo personalizzato. Per informazioni dettagliate su come eseguire questa operazione in Windows 10, vedere l'articolo [creare un oggetto Criteri di gruppo](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .
  
