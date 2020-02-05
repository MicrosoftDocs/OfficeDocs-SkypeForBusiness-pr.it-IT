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
description: 'Riepilogo: Panoramica dei metodi di installazione client aziendali per Skype for business.'
ms.openlocfilehash: 0e7859fe207ed80aa7dceef794aa57d15cc0c79b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768729"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>Distribuire client per Skype for Business Server
 
**Riepilogo:** Panoramica dei metodi di installazione client Enterprise per Skype for business.
  
La modalità di distribuzione di Skype for business agli utenti dipende dal fatto che sia stato acquistato Skype for business come parte di un piano di Office 365 oppure che sia stata acquistata una versione con contratto multilicenza di Skype for business. 
  
- **Office 365** Se si ha un piano di Office 365 che include Skype for business, la tecnologia di installazione usata viene chiamata a portata di clic. Con Office 365 puoi consentire agli utenti di installare Skype for business dal portale di Office 365. In alternativa, è possibile distribuire Skype for business agli utenti scaricando il software nella rete locale e usando gli strumenti di distribuzione del software esistenti, ad esempio con Microsoft endpoint Configuration Manager. Per informazioni sull'installazione di Skype for business incluso in Office 365, vedere [distribuire il client Skype for business in office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).
    
- **Contratti multilicenza** Se si ha una versione con contratto multilicenza del client Skype for business 2015 o 2016, la tecnologia di installazione usata è Windows Installer (MSI). Un pacchetto di installazione basato su Windows Installer è costituito da più file MSI. Un pacchetto MSI di base indipendente dalla lingua viene combinato con uno o più pacchetti specifici della lingua per creare un prodotto completo. La configurazione assembla i singoli pacchetti ed esegue le attività di personalizzazione e manutenzione durante e dopo l'installazione di Office nei computer degli utenti. Il client Skype for business 2019 usa programmi di installazione a portata di clic.
    
Gli argomenti in questa sezione descrivono come usare e personalizzare Windows Installer per distribuire il client Skype for business agli utenti tramite le normali procedure.
  
> [!NOTE]
> Il componente aggiuntivo riunione Skype per Microsoft Office, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, viene installato automaticamente con i client Skype for business. 
  
> [!NOTE]
> Il programma di installazione di Office 365 non disinstalla versioni precedenti di Lync. Il client Skype for business installa affiancato ad altri client Lync. 
  
## <a name="installing-windows-clients"></a>Installazione di client Windows

- [Personalizzare l'installazione del client Windows in Skype for Business Server](customize-windows-client-installation.md)
    
- [Configurare l'esperienza client con Skype for Business](configure-the-client-experience.md)
    
- [Configurare l'elenco contatti intelligenti in Skype for Business Server](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>Installazione dei client di dispositivi

- [Installare e testare Skype for business per Windows Phone](windows-phone.md)
    
- [Installare e testare Skype for business per iOS](ios.md)
    
    
- [Distribuire il plug-in di Lync VDI con Skype for Business Server](deploy-the-lync-vdi-plug-in.md)
    
- [Distribuire client scaricabili Web in Skype for Business Server](deploy-web-downloadable-clients.md)
    
- [Personalizzare l'esperienza del client Mac in Skype for business](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>Vedere anche

[Distribuire il client Skype for business in Office 365](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
