# ffmpeg-wrapper-
This is my ffmpeg wrapper for old Samsung TV and Sharp, using GTX Nvidia 1050ti 4gb on ubuntu server for transcoding Serviio 
 Serviio FFmpeg Wrapper (Samsung MU6172, Samsung Force, Sharp Aquos Android)
#
# Features:
# - Detects Serviio probe vs real transcode → passthrough probes untouched
# - Rewrites video codec to NVENC (h264_nvenc / hevc_nvenc) if requested
# - Strips unsupported Serviio filters (-qscale, subtitles filter graph, movflags +dash)
# - Strips/rewrites -map [v] → -map 0:v:0 (fix missing video stream issue)
# - Samsung: forces safe MP4 (+faststart, avoid_negative_ts) or MPEGTS fallback
# - Non-Samsung: auto-fix fragmented MP4 (+faststart for seeking)
# - Sharp Aquos: minimal transcoding
# - Normalizes AAC audio → MP3 stereo 48kHz (Samsung requirement)
# - NVENC retry logic: vbr → fallback libx264 (superfast)
# - Hardsub retry with SRT if subs present and transcode fails