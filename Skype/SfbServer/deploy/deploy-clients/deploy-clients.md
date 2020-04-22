---
title: Distribuire client per Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Riepilogo: Panoramica dei metodi di installazione client Enterprise per Skype for business.'
ms.openlocfilehash: cdee3db6dc6fcec646ee2e15b6aeebc298d75b67
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778282"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Distribuire client per Skype for Business Server
 
**Riepilogo:** Panoramica dei metodi di installazione client Enterprise per Skype for business.
  
La modalità di distribuzione di Skype for business agli utenti dipende dal fatto che l'utente abbia acquistato Skype for business come parte di un piano di Office 365 o che sia stata acquistata una versione con contratto multilicenza di Skype for business. 
  
- **Office 365** Se si dispone di un piano di Office 365 che include Skype for business, la tecnologia di installazione utilizzata viene chiamata a portata di clic. Con Office 365, è possibile consentire agli utenti di installare Skype for business per se stessi dall'interfaccia di amministrazione di Microsoft 365. In alternativa, è possibile distribuire Skype for business agli utenti scaricando il software nella rete locale e quindi utilizzando gli strumenti di distribuzione del software esistenti, ad esempio con Microsoft endpoint Configuration Manager. Per informazioni sull'installazione di Skype for business disponibile con Office 365, vedere [deploy the Skype for Business client in office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Contratti multilicenza** Se si dispone di una versione con contratto multilicenza del client Skype for business 2015 o 2016, la tecnologia di installazione utilizzata è Windows Installer (MSI). Un pacchetto di installazione basato su Windows Installer è costituito da più file MSI. La creazione di un prodotto completo si basa sulla combinazione di un pacchetto MSI principale indipendente dalla lingua con uno o più pacchetti specifici della lingua. I singoli pacchetti vengono assemblati durante l'installazione mentre le attività di personalizzazione e manutenzione vengono eseguite durante e dopo l'installazione di Office nei computer degli utenti. Il client Skype for business 2019 utilizza programmi di installazione a portata di clic.
    
Negli argomenti di questa sezione viene descritto come utilizzare e personalizzare il programma di installazione di Windows per distribuire il client Skype for business agli utenti tramite le procedure normali.
  
> [!NOTE]
> Il componente aggiuntivo per riunioni Skype per Microsoft Office, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, viene installato automaticamente con i client Skype for business. 
  
> [!NOTE]
> Il programma di installazione di Office 365 non disinstalla le versioni precedenti di Lync. Il client Skype for business installa affiancati con altri client Lync. 
  
## <a name="installing-windows-clients"></a>Installazione dei client Windows

- [Personalizzare l'installazione di Windows client in Skype for Business Server](customize-windows-client-installation.md)
    
- [Configurare l'esperienza client con Skype for business](configure-the-client-experience.md)
    
- [Configurare l'elenco dei contatti intelligenti in Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installazione dei client del dispositivo

- [Installare e testare Skype for business per Windows Phone](windows-phone.md)
    
- [Installare e testare Skype for business per iOS](ios.md)
    
    
- [Distribuire il plug-in VDI di Lync con Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Distribuire i client scaricabili Web in Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Personalizzare l'esperienza client Mac in Skype for business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Vedere anche

[Distribuire il client Skype for business in Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
