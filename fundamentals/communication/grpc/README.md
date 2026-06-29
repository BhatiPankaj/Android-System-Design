# gRPC

## What is gRPC?

gRPC is a high-performance communication protocol developed by Google.

It uses:
* **HTTP/2**
* **Protocol Buffers** (binary serialization)

instead of JSON.

---

## Why gRPC Is Fast

REST typically sends data in **JSON text** format.

**JSON Example:**
```json
{
  "latitude": 12.23,
  "longitude": 77.89
}
```
JSON contains extra characters (quotes, braces, keys) and consumes more bandwidth.

**gRPC** sends compact **binary data**.
* **Smaller payload:** Highly compressed compared to text.
* **Faster transmission:** Less data to send over the wire.

---

## How gRPC Works

Client and server define a contract using a `.proto` file.

**Example Protobuf:**
```protobuf
message UserRequest {
  int32 user_id = 1;
}

message UserResponse {
  string name = 1;
}

service UserService {
  rpc GetUser(UserRequest) returns (UserResponse);
}
```

Code is generated automatically for various languages.

**Communication flow:**
1. **Mobile App** calls the generated method.
2. **gRPC Client Stub** handles the call.
3. **Protocol Buffer Serialization** (Binary) occurs.
4. **HTTP/2** transport layer sends the binary.
5. **Server** receives and processes.
6. **Binary Response** is sent back.
7. **Protocol Buffer Deserialization** converts binary back to an object.
8. **App** receives the final object.

---

## Streaming Support

Unlike standard REST, gRPC supports continuous streaming out of the box.

**Types:**
* **Unary:** One request, one response (standard call).
* **Server Streaming:** Server continuously sends data to the client.
* **Client Streaming:** Client continuously sends data to the server.
* **Bidirectional Streaming:** Both client and server continuously communicate.

---

## Advantages

* **Very fast:** Significant performance gains over REST.
* **Smaller payload size:** Binary serialization is much more efficient than JSON.
* **Lower latency:** Thanks to HTTP/2 multiplexing and binary format.
* **Supports streaming:** Built-in support for various streaming models.
* **Efficient:** Ideal for high-throughput systems and battery-constrained mobile devices.

---

## Disadvantages

* **Infrastructure complexity:** Requires HTTP/2 support end-to-side.
* **Harder debugging:** Binary payloads are not human-readable without specialized tools (unlike JSON).
* **Less common:** Fewer public APIs use gRPC compared to REST/GraphQL.
* **Setup overhead:** Requires proto definition and code generation steps.

---

## Mobile Use Cases

gRPC is suitable for:
* **Google Maps location updates:** High frequency, small updates.
* **Internal microservices:** Communication between internal app modules or dedicated backend services.
* **Realtime streaming systems:** Live audio/video metadata or status updates.
* **Performance-critical internal services:** Where every millisecond and byte counts.

---

## When NOT to Use gRPC

Avoid when:
* Standard request-response APIs are sufficient for the use case.
* Simplicity and quick prototyping are preferred.
* The public API ecosystem you are integrating with already uses REST.

**Examples:**
* YouTube Search
* E-commerce product listing

---

## Interview Decision Example

**Question:**
Design Uber Driver Tracking

**Reasoning:**
* Location updates happen continuously (high frequency).
* Low latency is critical for a smooth user experience.
* Small payload size matters to save data and battery.
* **Streaming communication** is highly beneficial for real-time updates.

**Therefore:**
**gRPC** is a strong candidate for this use case.
