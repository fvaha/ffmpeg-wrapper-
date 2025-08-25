This is my ffmpeg wrapper for old Samsung TV and Sharp, using GTX Nvidia 1050ti 4gb on ubuntu server for transcoding Serviio 
 Serviio FFmpeg Wrapper (Samsung MU6172, Samsung Force, Sharp Aquos Android)

# ============================================================================
#  Features:
# - Detects Serviio "probe" vs real transcode → passthrough for probes
# - NVENC acceleration (h264_nvenc / hevc_nvenc) → retry → libx264 fallback
# - Strips unsupported filters (-qscale, subtitles, movflags mid-command)
# - Fixes invalid maps: -map [v] → -map 0:v:0
# - Containers:
#     * Samsung → MP4 +faststart (preferred), MPEGTS fallback
#     * Others → MP4 +faststart
# - Audio: For Samsung → MP3 stereo 48kHz 192kbit/s
# - Subtitles: only sidecar `.srt` with hardsub fallback
# ============================================================================
