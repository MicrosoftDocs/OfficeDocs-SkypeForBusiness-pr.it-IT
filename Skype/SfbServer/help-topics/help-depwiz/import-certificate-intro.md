---
title: Importare un certificato (Intro)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: Per importare un certificato, è necessario specificare il percorso del relativo file. Nella casella di testo Seleziona file di certificato è possibile digitare il percorso completo e il nome del file oppure fare clic sul pulsante Sfoglia e selezionare il percorso e il nome del file, in genere con estensione p7b, pfx o cer.
ms.openlocfilehash: 2ca89291376c488426001e1ff42c4925da58a3e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827286"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="5e45f-104">Importare un certificato (Intro)</span><span class="sxs-lookup"><span data-stu-id="5e45f-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="5e45f-p102">Per importare un certificato, è necessario specificare il percorso del relativo file. Nella casella di testo **Seleziona file di certificato** è possibile digitare il percorso completo e il nome del file oppure fare clic sul pulsante **Sfoglia** e selezionare il percorso e il nome del file, in genere con estensione p7b, pfx o cer.</span><span class="sxs-lookup"><span data-stu-id="5e45f-p102">To import a certificate, you must provide a path to the certificate file. In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="5e45f-107">Se il certificato contiene una chiave privata, selezionare la casella di controllo Il file di **certificato contiene la chiave privata del certificato.**</span><span class="sxs-lookup"><span data-stu-id="5e45f-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="5e45f-108">Quando questa casella di controllo è selezionata, viene abilitata la casella di immissione **Password**.</span><span class="sxs-lookup"><span data-stu-id="5e45f-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="5e45f-109">Se al certificato di cui si dispone è associata una chiave privata, in genere al momento della creazione del certificato viene impostata una password per tale chiave.</span><span class="sxs-lookup"><span data-stu-id="5e45f-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="5e45f-110">È necessario immettere la password della chiave privata per consentire l'importazione del certificato e della chiave privata nell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="5e45f-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="5e45f-111">Dopo avere specificato le informazioni relative al percorso del file del certificato e, facoltativamente, la password della chiave privata (se richiesta), fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5e45f-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5e45f-112">Se non si conosce la password della chiave privata, l'importazione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5e45f-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

