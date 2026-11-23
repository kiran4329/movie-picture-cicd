FROM public.ecr.aws/docker/library/node:18.14.2-alpine3.17

ARG REACT_APP_MOVIE_API_URL
ENV REACT_APP_MOVIE_API_URL=${REACT_APP_MOVIE_API_URL}

WORKDIR /app

# Copy dependency files
COPY package*.json ./

# Install packages
RUN npm ci

# Copy application code
COPY . .

# Build the app
RUN npm run build

# Expose the application port
EXPOSE 3000

# Start the React app
CMD ["npm", "run", "serve"]
