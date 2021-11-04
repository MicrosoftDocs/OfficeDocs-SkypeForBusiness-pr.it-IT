---
title: Distribuire client per Skype for Business Server
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Riepilogo: panoramica dei metodi di installazione dei client aziendali per Skype for Business.'
ms.openlocfilehash: 60da950c4ef330f704d45944a900e579478c558c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778926"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Distribuire client per Skype for Business Server
 
**Riepilogo:** Panoramica dei metodi di installazione dei client aziendali per Skype for Business.
  
La modalità di distribuzione di Skype for Business agli utenti dipende dal fatto che sia stato acquistato Skype for Business nell'ambito di un piano Microsoft 365 o Office 365 o che sia stata acquistata una versione con contratto multilicenza di Skype for Business. 
  
- **Microsoft 365 o Office 365** Se si dispone di un piano Microsoft 365 o Office 365 che include Skype for Business, la tecnologia di installazione utilizzata è denominata A livello di clic. Puoi consentire agli utenti di installare Skype for Business automaticamente dalla interfaccia di amministrazione di Microsoft 365. In caso contrario, è possibile distribuire Skype for Business agli utenti scaricando il software nella rete locale e quindi utilizzando gli strumenti di distribuzione del software esistenti, ad esempio con Microsoft Endpoint Configuration Manager. Per informazioni sull'Skype for Business in Microsoft 365 e Office 365, vedere Deploy [the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Contratti multilicenza** Se si dispone di una versione con contratto multilicenza del client Skype for Business 2015 o 2016, la tecnologia di installazione utilizzata è Windows Installer (MSI). Un Windows di installazione basato sul programma di installazione è costituito da più file MSI. La creazione di un prodotto completo si basa sulla combinazione di un pacchetto MSI principale indipendente dalla lingua con uno o più pacchetti specifici della lingua. I singoli pacchetti vengono assemblati durante l'installazione mentre le attività di personalizzazione e manutenzione vengono eseguite durante e dopo l'installazione di Office nei computer degli utenti. Il client Skype for Business 2019 usa i programmi di installazione A click-to-Run.
    
Negli argomenti di questa sezione viene descritto come utilizzare e personalizzare il programma di installazione di Windows per distribuire il client Skype for Business agli utenti tramite le procedure normali.
  
> [!NOTE]
> Il Riunione Skype aggiuntivo per Microsoft Office, che supporta la gestione delle riunioni dal client di messaggistica e collaborazione di Outlook, viene installato automaticamente con Skype for Business client. 
  
> [!NOTE]
> I Microsoft 365 e Office 365 non disinstallano le versioni precedenti di Lync. Il Skype for Business client viene installato affiancato ad altri client Lync. 
  
## <a name="installing-windows-clients"></a>Installazione di Windows client

- [Personalizzare Windows'installazione client in Skype for Business Server](customize-windows-client-installation.md)
    
- [Configurare l'esperienza client con Skype for Business](configure-the-client-experience.md)
    
- [Configurare l'elenco contatti smart in Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installazione dei client dei dispositivi

- [Installare e testare Skype for Business per Windows Phone](windows-phone.md)
    
- [Installare e testare Skype for Business per iOS](ios.md)
    
    
- [Distribuire il plug-in VDI di Lync con Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Distribuire client scaricabili web in Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Personalizzare l'esperienza del client Mac in Skype for Business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Vedere anche

[Distribuire il client Skype for Business in Microsoft 365 o Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
