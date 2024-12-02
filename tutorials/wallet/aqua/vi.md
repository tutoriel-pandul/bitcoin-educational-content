---
name: Aqua
description: Bitcoin, Lightning và Liquid trong một ví duy nhất
---
![cover](assets/cover.webp)

Aqua là một ứng dụng di động cho phép tạo ví nóng (hot wallet) dễ dàng cho Bitcoin và Liquid, đồng thời cung cấp khả năng sử dụng Lightning mà không cần phải quản lý node nhờ vào tính năng chuyển đổi tích hợp. Nó cũng hỗ trợ quản lý stablecoin USDT trên các mạng khác nhau.

Được phát triển bởi công ty JAN3 dưới sự lãnh đạo của Samson Mow, ứng dụng Aqua ban đầu được thiết kế đặc biệt cho nhu cầu của người dùng tại Mỹ Latinh, mặc dù nó phù hợp với bất kỳ người dùng nào trên toàn thế giới. Nó đặc biệt thú vị đối với người mới bắt đầu và những người sử dụng Bitcoin hàng ngày cho các giao dịch thanh toán của họ.

Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng nhiều tính năng của Aqua. Nhưng trước tiên, hãy dành một chút thời gian để hiểu về sidechain trên Bitcoin là gì và Liquid hoạt động như thế nào, điều này sẽ cho phép chúng ta hiểu rõ hơn về lợi ích của Aqua.

![AQUA](assets/fr/01.webp)

## Sidechain là gì?

Giao thức Bitcoin có những hạn chế kỹ thuật cố ý giúp duy trì sự phân quyền của mạng và đảm bảo sự phân phối an ninh cho tất cả người dùng. Tuy nhiên, những giới hạn này đôi khi khiến người dùng cảm thấy bất mãn, đặc biệt là trong thời điểm tắc nghẽn do lượng giao dịch đồng thời cao. Cuộc tranh luận về khả năng mở rộng của Bitcoin đã chia rẽ cộng đồng từ lâu, đặc biệt là trong suốt Cuộc chiến Blocksize. Kể từ đó, cộng đồng Bitcoin rộng rãi công nhận rằng khả năng mở rộng phải được đảm bảo bởi các giải pháp ngoài chuỗi, trên các hệ thống lớp thứ hai. Trong số các giải pháp này là sidechain, vẫn còn tương đối ít được biết đến và sử dụng so với các hệ thống khác như Lightning Network.

Sidechain là một blockchain độc lập hoạt động song song với blockchain chính của Bitcoin. Nó sử dụng bitcoin như một đơn vị tài khoản thông qua một cơ chế gọi là "*two-way peg*". Hệ thống này cho phép khóa bitcoin trên chuỗi chính để sao chép giá trị của chúng trên sidechain, nơi chúng lưu thông như các token được bảo đảm bởi bitcoin gốc. Những token này thường duy trì một giá trị tương đương với bitcoin đã khóa trên chuỗi chính, và quá trình này có thể được đảo ngược để lấy lại các quỹ trên Bitcoin.
Mục tiêu của sidechain là cung cấp các chức năng bổ sung hoặc cải tiến kỹ thuật, như giao dịch nhanh hơn, phí thấp hơn, hoặc hỗ trợ cho hợp đồng thông minh. Những đổi mới này không phải lúc nào cũng có thể được triển khai trực tiếp trên blockchain Bitcoin mà không làm ảnh hưởng đến sự phân quyền hoặc an ninh của nó. Sidechain do đó cho phép thử nghiệm và khám phá các giải pháp mới trong khi vẫn bảo toàn tính toàn vẹn của Bitcoin. Tuy nhiên, những giao thức này thường đòi hỏi những thỏa hiệp, đặc biệt là về phân quyền và an ninh, tùy thuộc vào mô hình quản trị và cơ chế đồng thuận được chọn.
## Liquid là gì?

Liquid là một sidechain liên kết được xây dựng trên Bitcoin, phát triển bởi Blockstream, nhằm mục đích tăng tốc độ, bảo mật và chức năng của giao dịch. Nó sử dụng một cơ chế neo hai chiều được thiết lập trên một liên minh để khóa bitcoin trên chuỗi chính và tạo ra Liquid-bitcoin (L-BTC), các token lưu thông trên Liquid trong khi vẫn được bảo đảm bởi bitcoin gốc.

![AQUA](assets/fr/02.webp)

Mạng Liquid dựa trên một liên minh các bên tham gia, bao gồm các thực thể được công nhận từ hệ sinh thái Bitcoin, những người này xác nhận các khối và quản lý việc neo hai chiều. Ngoài L-BTC, Liquid cũng cho phép phát hành các tài sản số khác, như stablecoin USDT hoặc các loại tiền điện tử khác.

![AQUA](assets/fr/03.webp)

## Cài đặt Ứng dụng Aqua

Bước đầu tiên tự nhiên là tải xuống ứng dụng Aqua. Đi đến cửa hàng ứng dụng của bạn:
- [Cho Android](https://play.google.com/store/apps/details?id=io.aquawallet.android);
- [Cho Apple](https://apps.apple.com/us/app/aqua-wallet/id6468594241).
![AQUA](assets/fr/04.webp)
Đối với người dùng Android, bạn cũng có tùy chọn cài đặt ứng dụng qua tệp `.apk` [có sẵn trên GitHub của họ](https://github.com/AquaWallet/aqua-wallet/releases).

![AQUA](assets/fr/05.webp)

Khởi chạy ứng dụng, sau đó đánh dấu vào ô "*Tôi đã đọc và đồng ý với Điều khoản Dịch vụ & Chính sách Bảo mật*".

![AQUA](assets/fr/06.webp)

## Tạo Ví của Bạn trên Aqua

Nhấn vào nút "*Tạo Ví*".

![AQUA](assets/fr/07.webp)

Và đó là, ví của bạn đã được tạo!

![AQUA](assets/fr/08.webp)

Nhưng trước hết, vì đây là một ví tự quản lý, việc tạo bản sao lưu vật lý cho cụm từ ghi nhớ của bạn là điều bắt buộc. **Cụm từ ghi nhớ này cung cấp quyền truy cập đầy đủ và không hạn chế vào tất cả bitcoin của bạn**. Bất kỳ ai sở hữu cụm từ này có thể ăn cắp tiền của bạn, ngay cả khi không có quyền truy cập vật lý vào điện thoại của bạn.
Nó cho phép bạn khôi phục quyền truy cập vào bitcoin của mình trong trường hợp mất mát, trộm cắp, hoặc hư hại điện thoại. Do đó, việc sao lưu cẩn thận trên một phương tiện vật lý (không phải kỹ thuật số) và lưu trữ nó ở một vị trí an toàn là rất quan trọng. Bạn có thể ghi chú nó trên một tờ giấy, hoặc để đảm bảo an toàn hơn, nếu ví này quan trọng, tôi khuyên bạn nên khắc nó trên một phương tiện bằng thép không gỉ để bảo vệ khỏi rủi ro của hỏa hoạn, lũ lụt, hoặc sụp đổ (đối với một ví nóng nhằm bảo vệ một lượng nhỏ bitcoin, một bản sao lưu giấy đơn giản có lẽ là đủ).
Để làm điều này, nhấn vào menu cài đặt.

![AQUA](assets/fr/09.webp)

Sau đó nhấn vào "*Xem Cụm từ Ghi nhớ*". Tạo một bản sao lưu vật lý cho cụm từ 12 từ này.

![AQUA](assets/fr/10.webp)

Trong cùng menu cài đặt này, bạn cũng có thể thay đổi ngôn ngữ của ứng dụng cũng như đơn vị tiền tệ fiat được sử dụng.

![AQUA](assets/fr/11.webp)

Trước khi nhận bitcoin đầu tiên vào ví của bạn, **tôi khuyên bạn nên thực hiện một bài kiểm tra khôi phục dự phòng**. Ghi chú lại một thông tin tham chiếu, như xpub của bạn hoặc địa chỉ nhận đầu tiên, sau đó xóa ví của bạn trên ứng dụng Aqua khi nó vẫn còn trống. Tiếp theo, thử khôi phục ví của bạn trên Aqua sử dụng bản sao lưu giấy của bạn. Kiểm tra xem thông tin chứng thực được tạo sau khi khôi phục có khớp với thông tin bạn đã ghi chú ban đầu hay không. Nếu đúng như vậy, bạn có thể yên tâm rằng bản sao lưu giấy của bạn là đáng tin cậy. Để tìm hiểu thêm về cách thực hiện bài kiểm tra khôi phục, tôi khuyên bạn nên tham khảo hướng dẫn khác này:

https://planb.network/tutorials/wallet/recovery-test

## Nhận bitcoins trên Aqua

Bây giờ ví của bạn đã được thiết lập, bạn đã sẵn sàng để nhận sats đầu tiên của mình! Chỉ cần nhấn vào nút "*Nhận*" trong menu "*Ví*".

![AQUA](assets/fr/12.webp)

Bạn có thể chọn nhận bitcoins trên onchain, trên Liquid, hoặc qua Lightning.

![AQUA](assets/fr/13.webp)

Đối với giao dịch onchain, Aqua sẽ tạo một địa chỉ nhận cụ thể nơi bạn có thể nhận sats của mình.

![AQUA](assets/fr/14.webp)

Tương tự, khi chọn Liquid, Aqua sẽ cung cấp cho bạn một địa chỉ Liquid.

![AQUA](assets/fr/15.webp)

Nếu bạn muốn nhận tiền qua Lightning, bạn sẽ cần phải chỉ định số lượng mong muốn trước.

![AQUA](assets/fr/16.webp)

Sau đó, nhấn vào "*Tạo Hóa đơn*".

![AQUA](assets/fr/17.webp)
Aqua sẽ tạo một hóa đơn để nhận tiền từ ví Lightning. Điều quan trọng cần lưu ý là, khác với các tùy chọn onchain và Liquid, tiền nhận qua Lightning sẽ được tự động chuyển đổi thành L-BTC trên Liquid sử dụng công cụ Boltz, vì Aqua không phải là một nút Lightning. Quy trình này cho phép bạn nhận và gửi tiền qua Lightning, nhưng không bao giờ giữ bitcoin của bạn trên Lightning.![AQUA](assets/fr/18.webp)

Cá nhân tôi sẽ bắt đầu bằng cách gửi bitcoin qua Lightning đến Aqua. Một khi giao dịch hoàn tất với hóa đơn được cung cấp, một xác nhận sẽ được nhận.

![AQUA](assets/fr/19.webp)

Để theo dõi tiến trình của việc chuyển đổi, quay trở lại trang chủ của ví và nhấp vào tài khoản "*L2 Bitcoin*", nơi liệt kê các giao dịch Lightning (qua chuyển đổi) và Liquid.

![AQUA](assets/fr/20.webp)

Tại đây, bạn có thể xem giao dịch của mình cũng như số dư L-BTC của bạn.

![AQUA](assets/fr/21.webp)

## Chuyển đổi bitcoin với Aqua

Bây giờ bạn đã có tài sản trong ví Aqua của mình, bạn có tùy chọn để chuyển đổi chúng trực tiếp từ ứng dụng, hoặc để chuyển chúng sang blockchain Bitcoin chính thống hoặc sang Liquid. Bạn cũng có thể chuyển đổi bitcoin của mình thành stablecoin USDT (hoặc các loại khác). Để làm điều này, truy cập menu "*Marketplace*".

![AQUA](assets/fr/22.webp)

Nhấp vào "*Swaps*".

![AQUA](assets/fr/23.webp)

Trong hộp "*Transfer from*", chọn tài sản bạn muốn trao đổi. Hiện tại, tôi chỉ có L-BTC, vì vậy đó là lựa chọn của tôi.

![AQUA](assets/fr/24.webp)

Trong hộp "*Transfer to*", chọn tài sản mục tiêu của việc chuyển đổi của bạn. Về phần mình, tôi đã chọn USDT trên mạng Liquid.

![AQUA](assets/fr/25.webp)

Nhập số lượng bạn muốn chuyển đổi.

![AQUA](assets/fr/26.webp)

Xác nhận bằng cách nhấp vào "*Continue*".

![AQUA](assets/fr/27.webp)

Đảm bảo các thiết lập chuyển đổi phù hợp với bạn, sau đó xác nhận bằng cách trượt nút "*Swap*" ở cuối màn hình.

![AQUA](assets/fr/28.webp)

Việc chuyển đổi của bạn giờ đây đã được xác nhận.

![AQUA](assets/fr/29.webp)

Nếu chúng ta quay trở lại ví của mình, chúng ta có thể thấy rằng bây giờ chúng ta có USDT trên Liquid.

![AQUA](assets/fr/30.webp)

## Gửi bitcoin với Aqua

Bây giờ bạn đã có bitcoin trong ví Aqua của mình, bạn có tùy chọn để gửi chúng. Nhấp vào nút "*Send*".

![AQUA](assets/fr/31.webp)

Chọn tài sản bạn muốn gửi hoặc chọn mạng để thực hiện giao dịch. Về phần mình, tôi sẽ gửi bitcoin qua Lightning.

![AQUA](assets/fr/32.webp)
Tiếp theo, nhập thông tin cần thiết để gửi thanh toán: đối với Bitcoin onchain hoặc Liquid, bạn cần nhập địa chỉ nhận; đối với Lightning, một hóa đơn là cần thiết. Bạn có thể dán thông tin này trực tiếp vào trường được chỉ định hoặc sử dụng biểu tượng mã QR để mở camera và quét địa chỉ hoặc hóa đơn. Sau đó nhấp vào "*Continue*".
![AQUA](assets/fr/33.webp)

Nhấp vào "*Continue*" một lần nữa nếu tất cả thông tin xuất hiện chính xác.

![AQUA](assets/fr/34.webp)
Aqua sau đó sẽ hiển thị cho bạn một bản tóm tắt của giao dịch. Đảm bảo tất cả thông tin là chính xác, đặc biệt là địa chỉ đích, phí giao dịch và số lượng. Để xác nhận giao dịch, hãy trượt nút "*Slide to send*" nằm ở cuối màn hình.
![AQUA](assets/fr/35.webp)

Sau đó, bạn sẽ nhận được xác nhận về việc gửi tiền.

![AQUA](assets/fr/36.webp)

Và đó là tất cả, bạn giờ đây đã biết cách sử dụng ứng dụng Aqua để nhận và chi tiêu tiền trên Bitcoin, Lightning và Liquid, tất cả từ một giao diện duy nhất.

Nếu bạn thấy hướng dẫn này hữu ích, tôi sẽ rất biết ơn nếu bạn có thể để lại một lượt thích ở phía dưới. Đừng ngần ngại chia sẻ bài viết này trên các mạng xã hội của bạn. Cảm ơn bạn rất nhiều!

Tôi cũng khuyên bạn nên xem qua hướng dẫn hoàn chỉnh khác này về ứng dụng di động Blockstream Green, đây là một giải pháp thú vị khác để thiết lập ví Liquid của bạn:

https://planb.network/tutorials/wallet/blockstream-green-liquid