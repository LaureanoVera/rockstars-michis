<script>
  export let status;
  export let message;

  const HTTP = {
    400: "BAD_REQUEST",
    401: "UNAUTHORIZED",
    403: "FORBIDDEN",
    404: "NOT_FOUND",
    500: "INTERNAL_SERVER_ERROR",
    503: "SERVICE_UNAVAILABLE",
    504: "GATEWAY_TIMEOUT",
  };
</script>

<span class="Error">
  Type: {HTTP[status].toLowerCase()} <br />
  Message: {message}
</span>
