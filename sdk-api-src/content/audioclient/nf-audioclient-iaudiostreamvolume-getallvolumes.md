---
UID: NF:audioclient.IAudioStreamVolume.GetAllVolumes
title: IAudioStreamVolume::GetAllVolumes (audioclient.h)
description: The GetAllVolumes method retrieves the volume levels for all the channels in the audio stream.
helpviewer_keywords: ["GetAllVolumes","GetAllVolumes method [Core Audio]","GetAllVolumes method [Core Audio]","IAudioStreamVolume interface","IAudioStreamVolume interface [Core Audio]","GetAllVolumes method","IAudioStreamVolume.GetAllVolumes","IAudioStreamVolume::GetAllVolumes","IAudioStreamVolumeGetAllVolumes","audioclient/IAudioStreamVolume::GetAllVolumes","coreaudio.iaudiostreamvolume_getallvolumes"]
old-location: coreaudio\iaudiostreamvolume_getallvolumes.htm
tech.root: CoreAudio
ms.assetid: 6469ae01-d84d-4711-9b1e-cd8e685fcdd8
ms.date: 12/05/2018
ms.keywords: GetAllVolumes, GetAllVolumes method [Core Audio], GetAllVolumes method [Core Audio],IAudioStreamVolume interface, IAudioStreamVolume interface [Core Audio],GetAllVolumes method, IAudioStreamVolume.GetAllVolumes, IAudioStreamVolume::GetAllVolumes, IAudioStreamVolumeGetAllVolumes, audioclient/IAudioStreamVolume::GetAllVolumes, coreaudio.iaudiostreamvolume_getallvolumes
f1_keywords:
- audioclient/IAudioStreamVolume.GetAllVolumes
dev_langs:
- c++
req.header: audioclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista [desktop apps only]
req.target-min-winversvr: Windows Server 2008 [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Audioclient.h
api_name:
- IAudioStreamVolume.GetAllVolumes
targetos: Windows
req.typenames: 
req.redist: 
ms.custom: 19H1
---

# IAudioStreamVolume::GetAllVolumes


## -description



The <b>GetAllVolumes</b> method retrieves the volume levels for all the channels in the audio stream.




## -parameters




### -param dwCount [in]

The number of elements in the <i>pfVolumes</i> array. The <i>dwCount</i> parameter must equal the number of channels in the stream format. To get the number of channels, call the <a href="https://docs.microsoft.com/windows/desktop/api/audioclient/nf-audioclient-iaudiostreamvolume-getchannelcount">IAudioStreamVolume::GetChannelCount</a> method.


### -param pfVolumes [out]

Pointer to an array of volume levels for the channels in the audio stream. This parameter points to a caller-allocated <b>float</b> array into which the method writes the volume levels for the individual channels. Volume levels are in the range 0.0 to 1.0.


## -returns



If the method succeeds, it returns S_OK. If it fails, possible return codes include, but are not limited to, the values shown in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameter <i>dwCount</i> does not equal the number of channels in the stream.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
Parameter <i>pfVolumes</i> is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>AUDCLNT_E_DEVICE_INVALIDATED</b></dt>
</dl>
</td>
<td width="60%">
The audio endpoint device has been unplugged, or the audio hardware or associated hardware resources have been reconfigured, disabled, removed, or otherwise made unavailable for use.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>AUDCLNT_E_SERVICE_NOT_RUNNING</b></dt>
</dl>
</td>
<td width="60%">
The Windows audio service is not running.

</td>
</tr>
</table>
 




## -remarks



Clients can call the <a href="https://docs.microsoft.com/windows/desktop/api/audioclient/nf-audioclient-iaudiostreamvolume-setallvolumes">IAudioStreamVolume::SetAllVolumes</a> or <a href="https://docs.microsoft.com/windows/desktop/api/audioclient/nf-audioclient-iaudiostreamvolume-setchannelvolume">IAudioStreamVolume::SetChannelVolume</a> method to set the per-channel volume levels in an audio stream.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/audioclient/nn-audioclient-iaudiostreamvolume">IAudioStreamVolume Interface</a>



<a href="https://docs.microsoft.com/windows/desktop/api/audioclient/nf-audioclient-iaudiostreamvolume-getchannelcount">IAudioStreamVolume::GetChannelCount</a>



<a href="https://docs.microsoft.com/windows/desktop/api/audioclient/nf-audioclient-iaudiostreamvolume-setallvolumes">IAudioStreamVolume::SetAllVolumes</a>



<a href="https://docs.microsoft.com/windows/desktop/api/audioclient/nf-audioclient-iaudiostreamvolume-setchannelvolume">IAudioStreamVolume::SetChannelVolume</a>
 

 

