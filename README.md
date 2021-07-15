# c-trader-indicator-low-volatility

Using Bollinger Band Squeeze to detect a period of loew volatility

## How to do ?

- Tìm hiểu về Bollinger Bands công thức ?
  - Công thức gồm những thành phần gì ?
  - Ứng dụng của Bollinger Bands

- Khoảng thắt (Squeeze) của Bollinger có ý nghĩa gì ?
- Dựa vào khoảng thắt tìm định nghĩa cho cách tìm khoảng low volatility.
- Trình bày pseudocode trước khi code vào file README.md

## Done

- Bollinger Bands có ba đường BOLU, BOLD, SMA thường dùng range 20.
  - Công thức:

    ```js
    BOLU=MA(TP,n)+m*σ[TP,n]
    BOLD=MA(TP,n)−m*σ[TP,n]
    ```

  - Như vậy, công thức trên phản ánh sự giao động của thị trường. Bollinger Bands rộng --> thị trường giao động mạnh, Bollinger Bands hẹp --> Thị trường giao động ít.
  - Khoảng thắt của BB phản ánh có thể có cơ hội giao dịch (vì thường thị trường giao động ít sẽ có những biến động lớn sau đó, giá đi lên hoặc đi xuống rõ rệt).
  - Như vậy cần tìm các khoảng thắt này cần định nghĩa:
    - **Khoảng cách tối thiếu của BOLU và BOLD với đường SMA để coi là khoảng thắt**
    - **Số nến tối thiếu để coi là 1 khoảng thắt.**
    - **Có cần sửa range 20 không ?  Cần backtest với các indicator để rõ hơn.**
