# Hướng dẫn Kiểm thử Tự động với Maestro trên Android Studio Emulator

Thư mục này chứa các kịch bản kiểm thử tự động (Automated E2E Flows) bằng công cụ **Maestro** cho ứng dụng di động Android (`ctu_voices_android`).

## 1. Yêu cầu Tiền đề (Prerequisites)

1. **Maestro CLI**: Đã được cài đặt tại `~/.maestro/bin/maestro` (Version: 2.8.0+).
2. **Java JDK**: JDK 17+ hoặc JDK 25 (Đã sẵn sàng trên máy).
3. **Android Studio Emulator / Physical Device**:
   - Mở Android Studio -> AVD Manager -> Khởi chạy 1 Emulator (Android 11+).
   - Hoặc cắm thiết bị thật bật USB Debugging.
   - Kiểm tra kết nối ADB bằng lệnh: `adb devices`

## 2. Đường dẫn kịch bản Test (Flow Files)

- `android-chat-tc100-send-valid-text.yaml`: Automation flow cho TC-100 (Gửi tin nhắn hợp lệ).
- `android-chat-tc101-empty-text-validation.yaml`: Automation flow cho TC-101 (Kiểm tra tin nhắn rỗng).
- `android-chat-tc106-search-contact.yaml`: Automation flow cho TC-106 (Tìm kiếm liên hệ chat).

## 3. Lệnh thực thi (Execution Commands)

Export PATH nếu cần và thực thi kịch bản:

```bash
export PATH="$PATH:$HOME/.maestro/bin"

# 1. Chạy kịch bản TC-100 (Gửi tin nhắn)
maestro test /home/dylan/CODE/CTUVoices.Testing/automated-tests/maestro/android-chat-tc100-send-valid-text.yaml

# 2. Chạy toàn bộ các kịch bản trong thư mục Maestro
maestro test /home/dylan/CODE/CTUVoices.Testing/automated-tests/maestro/

# 3. Mở Studio UI hỗ trợ record/debug kịch bản trực quan
maestro studio
```

> **Lưu ý về App ID (Package Name):**
> - Khi chạy bản Build Android cài đặt APK (`.apk`), appId mặc định là `vn.edu.ctu.voices`.
> - Nếu chạy qua ứng dụng Expo Go trên Emulator, sửa dòng đầu tiên trong file `.yaml` từ `appId: vn.edu.ctu.voices` thành `appId: host.exp.exponent`.
