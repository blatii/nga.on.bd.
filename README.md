# nga.on.bd.
fdatbi


from mitmproxy import http

class ProxyInterceptor:
    def request(self, flow: http.HTTPFlow) -> None:
        # Modify request before sending to the server
        print(f"Intercepted request: {flow.request.url}")

    def response(self, flow: http.HTTPFlow) -> None:
        # Modify response before sending to the browser
        print(f"Intercepted response: {flow.response.status_code}")

addons = [ProxyInterceptor()]
